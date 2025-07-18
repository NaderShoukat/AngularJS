var your_css_above = `
.create-container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 90vh;
    background: #fafbff;
}
.create-card {
    background: #fff;
    padding: 2.2rem 2.2rem 1.8rem 2.2rem;
    border-radius: 14px;
    box-shadow: 0 8px 32px rgba(80, 120, 210, 0.09), 0 1.5px 6px rgba(50, 50, 90, 0.08);
    max-width: 440px;
    width: 100%;
    margin: 2.3rem 0;
}
.create-card h3 {
    text-align: center;
    margin-bottom: 1.5rem;
    font-weight: 700;
    font-size: 1.45rem;
    color: #223359;
    letter-spacing: 0.7px;
}
.form-label {
    font-weight: 600;
    margin-bottom: 0.5rem;
    margin-top: 0.7rem;
    color: #203040;
    font-size: 1rem;
    display: block;
    letter-spacing: 0.07em;
}
.form-control, .form-select {
    width: 100%;
    padding: 0.7rem 1rem;
    margin-bottom: 0.45rem;
    font-size: 1rem;
    border: 1px solid #d2d6dc;
    border-radius: 8px;
    background: #f6f8fb;
    transition: border 0.2s;
    min-height: 38px;
    box-sizing: border-box;
}
.form-control:focus, .form-select:focus {
    outline: none;
    border-color: #4a77ff;
    background: #f1f5fe;
}
textarea.form-control {
    min-height: 68px;
    max-height: 120px;
    resize: vertical;
}
.btn-primary {
    display: block;
    width: 100%;
    padding: 0.85rem 0;
    background: linear-gradient(90deg, #306BFF 70%, #0A4BFF 100%);
    border: none;
    color: #fff;
    font-size: 1.09rem;
    border-radius: 8px;
    font-weight: 600;
    margin-top: 1.3rem;
    box-shadow: 0 2px 12px 0 rgba(40,90,200,0.08);
    transition: background 0.2s;
    letter-spacing: 0.07em;
}
.btn-primary:hover {
    background: linear-gradient(90deg, #0A4BFF 90%, #306BFF 100%);
}
.date-row {
    display: flex;
    gap: 0.7rem;
}
.date-group {
    flex: 1;
    min-width: 0;
}
`;

var html = `
<div class="create-container">
  <div class="create-card">
    <h3>Create Notification</h3>
    <form>
      <label class="form-label" for="message">Message</label>
      <textarea class="form-control" id="message" placeholder="Enter notification message"></textarea>

      <label class="form-label" for="type">Types</label>
      <select class="form-select" id="type">
        <option>Ongoing</option>
        <option>One-time</option>
        <option>Template</option>
        <option>Release Notes</option>
      </select>

      <div class="date-row">
        <div class="date-group">
          <label class="form-label" for="startdate">Starting Date</label>
          <input type="date" class="form-control" id="startdate" placeholder="mm/dd/yyyy">
        </div>
        <div class="date-group">
          <label class="form-label" for="enddate">End Date</label>
          <input type="date" class="form-control" id="enddate" placeholder="mm/dd/yyyy">
        </div>
      </div>

      <label class="form-label" for="status">Status</label>
      <select class="form-select" id="status">
        <option>Published</option>
        <option>Draft</option>
        <option>Queued</option>
      </select>

      <label class="form-label" for="createdby">Created By</label>
      <select class="form-select" id="createdby">
        <option>Name1</option>
        <option>Name2</option>
        <option>Name3</option>
      </select>

      <button type="submit" class="btn-primary">Submit Notification</button>
    </form>
  </div>
</div>
`;

$('.workarea').html('<style>' + your_css_above + '</style>' + html);
this.highlightTab && this.highlightTab();
