<style>
/* Card Centering */
.create-container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 70vh;
}
.create-card {
    background: #fff;
    padding: 2.5rem 2rem 1.5rem 2rem;
    border-radius: 14px;
    box-shadow: 0 6px 32px rgba(80,80,120,0.10), 0 1.5px 6px rgba(50,50,90,0.08);
    max-width: 420px;
    width: 100%;
}
.create-card h3 {
    text-align: center;
    margin-bottom: 1.5rem;
    font-weight: 700;
    font-size: 1.45rem;
    color: #20315d;
    letter-spacing: 0.2px;
}
.form-label {
    font-weight: 500;
    margin-bottom: 0.3rem;
    color: #232950;
    display: block;
}
.form-control, .form-select {
    width: 100%;
    padding: 0.55rem 0.9rem;
    font-size: 1rem;
    border: 1.5px solid #dde2e6;
    border-radius: 8px;
    background: #f7f9fc;
    margin-bottom: 1rem;
    outline: none;
    transition: border 0.2s;
}
.form-control:focus, .form-select:focus {
    border: 1.5px solid #0d6efd;
    background: #fff;
}
.btn-primary {
    width: 100%;
    padding: 0.65rem 0;
    border: none;
    border-radius: 8px;
    font-size: 1.1rem;
    font-weight: 600;
    background: linear-gradient(90deg,#2a60ee 60%, #3972f6 100%);
    color: #fff;
    box-shadow: 0 2px 8px rgba(80,120,255,0.11);
    cursor: pointer;
    transition: background 0.18s;
}
.btn-primary:hover {
    background: linear-gradient(90deg,#3972f6 60%, #2a60ee 100%);
}
</style>






var html = `
<div class="create-container">
    <div class="create-card">
        <h3>Create Notification</h3>
        <form>
            <label class="form-label">Message</label>
            <textarea class="form-control" placeholder="Enter notification message"></textarea>
            <label class="form-label">Types</label>
            <select class="form-select">
                <option>Ongoing</option>
                <option>Template</option>
                <option>Release Notes</option>
            </select>
            <label class="form-label">Starting Date</label>
            <input type="date" class="form-control"/>
            <label class="form-label">End Date</label>
            <input type="date" class="form-control"/>
            <label class="form-label">Status</label>
            <select class="form-select">
                <option>Published</option>
                <option>Draft</option>
                <option>Queued</option>
            </select>
            <label class="form-label">Created By</label>
            <select class="form-select">
                <option>Name1</option>
                <option>Name2</option>
                <option>Name3</option>
            </select>
            <button type="submit" class="btn btn-primary">Submit Notification</button>
        </form>
    </div>
</div>
`;
$('.workarea').html('<style>' + your_css_above + '</style>' + html);
