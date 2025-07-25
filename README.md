public IEnumerable<IResult> AddNewFolder()
{
    // TEMP: Directly create "IT Files" under root

    using (var broker = _folderBrokerFactoryDelegate.Invoke())
    {
        var tag = broker.Value.AddNewFolder(SelectedExaminationContext.ExaminationId, Model);
        if (tag == null)
            yield break;

        // Create the view model from tag
        var newFolder = (IExplorerItemViewModel)Children.FirstOrDefault(x => x.Id == tag.Id);
        if (newFolder == null)
            yield break;

        // Set display name to "IT Files"
        newFolder.DisplayName = "IT Files";

        // Add to root (outside any selected folder)
        Items.Add(newFolder); // Replace 'Items' if your root collection has a different name

        // Let user rename if needed
        newFolder.StartRename();
    }
}
