# Wikipedia-addition
Adding Wikipedia to display translated media directly
document.addEventListener('DOMContentLoaded', function () {
  var keywordInput = document.getElementById('keywordInput');
  var highlightButton = document.getElementById('highlightButton');

  highlightButton.addEventListener('click', function () {
    chrome.tabs.query({ active: true, currentWindow: true }, function (tabs) {
      chrome.tabs.sendMessage(tabs[0].id, { action: 'highlight', keyword: keywordInput.value });
    });
  });
});
