define(['models/ExamDocumentType'], function (ExamDocumentType) {
    var examDocumentTypeCollection = Backbone.Collection.extend({
        // url: getDataServiceUrl() + '/DocumentType?$format=json', // Not needed anymore
        model: ExamDocumentType,

        sync: function (method, collection, options) {
            // Hardcoded static JSON data
            var response = {
                d: {
                    results: [
                        {
                            id: 1,
                            name: "Hardcoded Doc 1",
                            description: "This document is static JSON",
                            documenttype: "HDOC1"
                        },
                        {
                            id: 2,
                            name: "Hardcoded Doc 2",
                            description: "Another hardcoded doc",
                            documenttype: "HDOC2"
                        }
                        // Add more objects as needed
                    ]
                }
            };
            collection.add(response.d.results, { silent: true });
            collection.trigger('reset');
            if (options.success !== undefined)
                options.success(collection.models);
        }
        // initialize: function() {} // Optional, can be left out if empty
    });

    return examDocumentTypeCollection;
});
