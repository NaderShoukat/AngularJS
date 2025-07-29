public PublicFolder GetITFilesFolder(Guid examinationId)
{
    const string itFolderName = "IT Files";

    var itFolder = UnitOfWork.Set<Folder>()
        .OfType<PublicFolder>()
        .FirstOrDefault(x => x.ExaminationId == examinationId && x.Parent == null && x.Name == itFolderName);

    return itFolder;
}


var itFolder = broker.Value.GetITFilesFolder();
if (itFolder != null)
{
    var itFolderVM = _currentObjectScope.Resolve<IPublicFolder, IPublicFolderViewModel>(itFolder);
    _explorerItems.Add(itFolderVM);
}
