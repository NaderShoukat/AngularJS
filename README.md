sync: function (method, collection, options) {
    // Static data example: adjust properties to what your UI expects
    var response = {
        items: [
            {
                id: 101,
                name: "Relation A",
                description: "Sample relation record"
            },
            {
                id: 102,
                name: "Relation B",
                description: "Another relation"
            }
            // Add more as needed
        ]
    };
    collection.add(response.items, { silent: true });
    collection.trigger('reset');
    if (options.success !== undefined)
        options.success(collection.models);
}








sync: function (method, collection, options) {
    // Static data example
    var response = {
        d: {
            results: [
                {
                    id: 201,
                    name: "Type X",
                    description: "Document type X"
                },
                {
                    id: 202,
                    name: "Type Y",
                    description: "Document type Y"
                }
                // Add more as needed
            ]
        }
    };
    collection.add(response.d.results, { silent: true });
    collection.trigger('reset');
    if (options.success !== undefined)
        options.success(collection.models);
}
