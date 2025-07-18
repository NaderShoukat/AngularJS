var html = `
<div class="d-flex justify-content-center align-items-center" style="min-height:80vh;">
  <div class="card shadow" style="padding:32px 24px; max-width:550px; width:100%; border-radius:16px;">
    <h4 class="mb-4 fw-bold">Create Notification</h4>
    <form>
      <div class="mb-3">
        <label class="form-label fw-semibold">Message</label>
        <textarea class="form-control" rows="3" placeholder="Enter notification message"></textarea>
      </div>
      <div class="mb-3">
        <label class="form-label fw-semibold">Types</label>
        <select class="form-select">
          <option>Template</option>
          <option>One-time</option>
          <option selected>Ongoing</option>
          <option>Release Notes</option>
        </select>
      </div>
      <div class="mb-3">
        <label class="form-label fw-semibold">Starting Date</label>
        <input type="date" class="form-control" placeholder="mm/dd/yyyy" />
      </div>
      <div class="mb-3">
        <label class="form-label fw-semibold">End Date</label>
        <input type="date" class="form-control" placeholder="mm/dd/yyyy" />
      </div>
      <div class="mb-3">
        <label class="form-label fw-semibold">Status</label>
        <select class="form-select">
          <option>Draft</option>
          <option>Queued</option>
          <option selected>Published</option>
        </select>
      </div>
      <div class="mb-4">
        <label class="form-label fw-semibold">Created By</label>
        <select class="form-select">
          <option>Name1</option>
          <option>Name2</option>
          <option selected>Name3</option>
        </select>
      </div>
      <button type="submit" class="btn btn-primary w-100 fw-bold">Submit Notification</button>
    </form>
  </div>
</div>
`;
$('.workarea').html(html);
