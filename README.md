public void AddITFilesRootFolder(Guid examinationId)
{
    const string itFolderName = "IT Files";

    var existing = UnitOfWork.Set<Folder>()
        .Where(x => x.ExaminationId == examinationId && x.Parent == null && x.Name == itFolderName)
        .FirstOrDefault();

    if (existing != null)
        return; // already exists

    var itFolder = new PublicFolder
    {
        Name = itFolderName,
        ExaminationId = examinationId,
        // Add other properties if needed, like CreatedDate, CreatedBy
    };

    Add(itFolder);
    UnitOfWork.Commit();
}
