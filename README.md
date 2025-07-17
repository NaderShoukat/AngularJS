// --- COMMENT OUT THE ORIGINAL FUNCTION BELOW ---
// that.download = function (successCallback, failureCallback) {
//     debugger;
//     var promise = $http.get(getDataServiceUrl() + '/DocumentType?$format=json');
//     promise.success(function (data, status, headers, config) {
//         var result = data.d.results;
//         successCallback(result);
//     });
//     if (failureCallback !== undefined) {
//         promise.error(failureCallback);
//     }
// };

// --- USE THIS HARDCODED VERSION INSTEAD ---
that.download = function (successCallback, failureCallback) {
    // Hardcoded document type data for frontend development
    var mockResults = [
        {
            "_metadata": {
                "uri": "https://example.com/ETS.../DocumentType('1')",
                "type": "ConfigurationServiceModel.DocumentType"
            },
            "description": "Report of Examination",
            "documenttype": "ROE",
            "id": "3CBBB0CD9E13B4A398A726661BDF1E",
            "systemDataSourceText": "ADMINSite",
            "systemActiveIndicator": 1
        },
        {
            "_metadata": {
                "uri": "https://example.com/ETS.../DocumentType('2')",
                "type": "ConfigurationServiceModel.DocumentType"
            },
            "description": "Entry Letter",
            "documenttype": "ENTRY",
            "id": "4AD7B0A3D3B24B1F8BC6C6FF12345678",
            "systemDataSourceText": "ADMINSite",
            "systemActiveIndicator": 1
        }
    ];
    // Simulate an asynchronous callback
    setTimeout(function () {
        successCallback(mockResults);
    }, 200);
};
