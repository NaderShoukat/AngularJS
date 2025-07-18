var html = `
        <div class="container mt-5">
            <div class="row justify-content-center">
                <div class="col-md-6">
                    <div class="card shadow p-4">
                        <div class="card-body">
                            <h3 class="card-title mb-4 text-center">Create Notification</h3>
                            <form>
                                <div class="mb-3">
                                    <label class="form-label">Message</label>
                                    <textarea class="form-control" placeholder="Enter notification message"></textarea>
                                </div>
                                <div class="mb-3">
                                    <label class="form-label">Types</label>
                                    <select class="form-select">
                                        <option>Ongoing</option>
                                        <option>Template</option>
                                        <option>Release Notes</option>
                                    </select>
                                </div>
                                <div class="mb-3">
                                    <label class="form-label">Starting Date</label>
                                    <input type="date" class="form-control"/>
                                </div>
                                <div class="mb-3">
                                    <label class="form-label">End Date</label>
                                    <input type="date" class="form-control"/>
                                </div>
                                <div class="mb-3">
                                    <label class="form-label">Status</label>
                                    <select class="form-select">
                                        <option>Published</option>
                                        <option>Draft</option>
                                        <option>Queued</option>
                                    </select>
                                </div>
                                <div class="mb-4">
                                    <label class="form-label">Created By</label>
                                    <select class="form-select">
                                        <option>Name1</option>
                                        <option>Name2</option>
                                        <option>Name3</option>
                                    </select>
                                </div>
                                <button type="submit" class="btn btn-primary w-100">Submit Notification</button>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        `;

        $('.workarea').html(html);
