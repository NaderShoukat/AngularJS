define([
    'models/DocxTemplate',
    'collections/DocxTemplateRelationCollection',
    'models/DocxTemplateRelation'
], function (DocxTemplate, DocxTemplateRelationCollection, DocxTemplateRelation) {
    debugger;
    var docxTemplateCollection = Backbone.Collection.extend({
        // url: getDataServiceUrl() + '/Template?$format=json&$select=id,name,confidentialIndicator,typeId&$inlinecount=allpages',
        model: DocxTemplate,
        comparator: 'name',

        // Override the sync method to prevent API calls and return empty data
        sync: function (method, collection, options) {
            console.log('Intercepted sync call for DocxTemplateCollection. Returning empty data.');
            
            // Simulate a successful response with empty results
            var emptyResponse = {
                d: {
                    results: []
                }
            };

            // Call the success callback with the empty data
            if (options.success) {
                options.success(emptyResponse, 'success', null); // Mimic jQuery.ajax success signature
            }

            // Return a deferred object that is immediately resolved
            var deferred = new $.Deferred();
            deferred.resolve(emptyResponse);
            return deferred.promise();
        },

        // Keep the parse method if it's used elsewhere, but it won't be called by our custom sync
        parse: function(response) {
            // This parse method expects data in response.d.results
            // If your hardcoded data doesn't have this structure, adjust accordingly.
            return response.d.results;
        },

        initialize: function() {
            // Original initialize function content
        },

        getSelecteditem: function () {
            var modelsArray = this.where({ selected: true });
            if (modelsArray.length > 0) {
                return modelsArray[0];
            }
            return null; // Return null if no selected item
        }
    });
    return docxTemplateCollection;
});
