# estimated-reading-time-with-pure-javascript
Calculate reading time of Your Article with This Few Lines of Code:
<script>
//function use to convert character into words
function get_text(el) {
    ret = "";
    var length = el.childNodes.length;
    for(var i = 0; i < length; i++) {
        var node = el.childNodes[i];
        if(node.nodeType != 8) {
            ret += node.nodeType != 1 ? node.nodeValue : get_text(node);
        }
    }
    return ret;
}
//main body in which all words exist                              
var words = get_text(document.getElementById('main-body'));
var count = words.split(' ').length;
var avg = 150;
var counted = count / avg;
var maincount = Math.round(counted)
//show output of code                              
document.getElementById("r-time").innerHTML = "&#10030; "+ maincount + " minute read";

</script> 
put: id='main-body' as <article id='main-body'> to calculate words
use: <div id='r-time'/> to show output of code.

