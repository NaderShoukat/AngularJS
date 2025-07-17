sync: function (method, collection, options) {
    // Hardcoded static JSON data (structure matches your table/view requirements)
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
                // Add more objects as needed for your demo
            ]
        }
    };

    // Add data to the collection as if it was fetched from an API
    collection.add(response.d.results, { silent: true });
    collection.trigger('reset');
    if (options.success !== undefined)
        options.success(collection.models);
}
