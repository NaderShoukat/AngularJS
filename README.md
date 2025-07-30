public class ITFolderViewModel : FolderViewModel, IITFolderViewModel
{
    public ITFolderViewModel(
        PublicFolder model,
        IStageUserInteraction userInteraction,
        ISelectedExaminationContext selectedExaminationContext,
        ILog logger,
        IEventAggregator eventAggregator,
        Func<IFolder, IGenericFolderViewModel> folderViewModelFactoryDelegate,
        Func<ExaminationFile, IImportedItemViewModel> importedItemViewModelFactoryDelegate,
        Func<ExaminationDocument, IWorkPaperViewModel> workPaperViewModelFactoryDelegate,
        Func<IWorkPaperDialogViewModel> addWorkpaperFactory,
        Func<IAddFolderViewModel> addFolderViewModelFactory,
        IComponentContext componentContext)
        : base(model, userInteraction, selectedExaminationContext, logger, eventAggregator,
              folderViewModelFactoryDelegate, importedItemViewModelFactoryDelegate,
              workPaperViewModelFactoryDelegate, addWorkpaperFactory,
              addFolderViewModelFactory, componentContext)
    {
    }

    // Optional: Override any folder-specific behavior here
}
