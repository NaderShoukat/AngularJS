var itFolder = broker.Value.GetITFilesFolder(_selectedExaminationContext.ExaminationId);
    if (itFolder != null)
        _itFolderRoot = _currentObjectScope.Resolve<IPublicFolder, IPublicFolderViewModel>(itFolder);

if (_itFolderRoot != null)
    _explorerItems.Add(_itFolderRoot);
