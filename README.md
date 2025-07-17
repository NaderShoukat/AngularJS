sync: function (method, collection, options) {
    // Return an empty data set, simulating "no records"
    var response = { d: { results: [] } };
    collection.add(response.d.results, { silent: true });
    collection.trigger('reset');
    if (options.success !== undefined)
        options.success(collection.models);
}
