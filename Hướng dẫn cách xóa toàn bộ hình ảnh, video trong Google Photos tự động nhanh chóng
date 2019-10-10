// Nhấn nút chọn hình ảnh, video và xóa
const ELEMENT_SELECTORS = {
    checkboxClass: '.ckGgle',
    deleteButton: 'button[title="Xóa"]',
    confirmationButton: '#yDmH0d > div.llhEMd.iWO5td > div > div.g3VIld.V639qd.bvQPzd.oEOLpc.Up8vH.J9Nfi.A9Uzve.iWO5td > div.XfpsVe.J9fJmf > button.VfPpkd-LgbsSe.VfPpkd-LgbsSe-OWXEXe-k8QpJ.nCP5yc.kHssdc.HvOprf'
}
// Tự động xóa toàn bộ hình ảnh, video trong Google Photos bởi https://gdrive.vip/
// Cấu hình thời gian (milliseconds)
const TIME_CONFIG = {
    delete_cycle: 7000,
    press_button_delay: 2000
};

let imageCount = 0;

let checkboxes;
let buttons = {
    deleteButton: null,
    confirmationButton: null
}

let deleteTask = setInterval(() => {

    checkboxes = document.querySelectorAll(ELEMENT_SELECTORS['checkboxClass']);

    if (checkboxes.length <= 0) {
        console.log("[THÔNG TIN] Không còn hình ảnh (video) để xóa.");
        clearInterval(deleteTask);
        console.log("[THÀNH CÔNG] Đã thoát.");
        return;
    }

    imageCount += checkboxes.length;

    checkboxes.forEach((checkbox) => { checkbox.click() });
    console.log("[THÔNG TIN] Đang xóa...", checkboxes.length, "hình ảnh (video)");

    setTimeout(() => {

        buttons.deleteButton = document.querySelector(ELEMENT_SELECTORS['deleteButton']);
        buttons.deleteButton.click();

        setTimeout(() => {
            buttons.confirmation_button = document.querySelector(ELEMENT_SELECTORS['confirmationButton']);
            buttons.confirmation_button.click();
        }, TIME_CONFIG['press_button_delay']);
    }, TIME_CONFIG['press_button_delay']);
}, TIME_CONFIG['delete_cycle']);
