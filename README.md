# gatechke.github.io

</head>
<body>
  <div id="wrap">
    <div id="header"></div>
    <!--<article style="width: 58%; padding-top: 6%; padding-left: 4%; padding-right:7%; text-align: left;" >-->
    <article style="text-align:left;">
      <div id="surround">
        <h1>Conference Deadlines</h1>
        <div id="currtime"></div>
        <br />
        Medical Image:<input type="checkbox" id="Medical Image"  onclick="" checked>
        Machine Learning:<input type="checkbox" id="Machine Learning"  onclick="" checked>
        AI:<input type="checkbox" id="AI"  onclick="" >
        Computational Biology:<input type="checkbox" id="Computational Biology"  onclick="" >
        Algorithms:<input type="checkbox" id="Algorithms"  onclick="" >
        Linguistics:<input type="checkbox" id="Linguistics"  onclick="" >
        <br />
        <div id="deadlinesdiv"></div>
        <br />
      </div>
    </article>
  </div>
</body>

<style type="text/css">
/* Some resetting */
body {
  font-family: Verdana, Helvetica, sans-serif;
  font-size: 12px;
  padding: 0;
  margin: 0;
  background-color: white;
  color: #222;
}
/* Main content div */
#surround {
  margin-left: auto;
  margin-right: auto;
  margin-top: 50px;
  width: 600px;
  background-color: white;
}
/* Div that contains all deadlines */
#deadlinesdiv {
}
#currtime {
  font-size: 14px;
}
#bottompart {
  text-align: center;
}
/* Page title */
h1 {
  display: inline;
  margin-right: 10px;
  font-size: 35px;
}
/* Maintained by @karpathy */
#signature {
  position: absolute;
  bottom: auto;
  right: 0;
  text-align: center;
  padding-bottom: 15px;
  padding-right: 30px;
  /*font-size: 14px;*/
}
/* The cells that contain each deadline */
.dd {
  padding: 10px;
  margin-bottom: 3px;
  background-color: #EEE;
  border: 1px solid #DDD;
  cursor: pointer;
  position: relative;
}
.dd:hover {
  background-color: #DDD;
  border: 1px solid #AAA;
  cursor: default;
}
/* Time left description div */
.tld {
  float: right;
  font-size: 18px;
  font-weight: bold;
  margin-top: 16px;
}
/* Area description div */
.ad {
  font-family: monospace;
}
/* Time description div */
.td {
}
/* Venue description div */
.vd {
  font-weight: bold;
  font-size: 16px;
}
/* Warning div */
.wd {
  position: absolute;
  bottom: 10px;
  right: 8px;
  color: #700;
  font-size: 10px;
}
</style>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.10.6/moment.min.js"></script>

<script type="text/javascript">
// DATABASE
var deadlines= new Array();
var shouldDisplay = {"Machine Learning": true,
                    "Algorithms": true,
                    "AI": true,
                    "Computational Biology": true,
                    "Linguistics": true,
                    "Medical Image": true
                    }
// Machine Learning
deadlines.push({
  venue: "MICCAI",
  area: "Medical Image",
  deadline: moment("2019-03-02 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "https://www.miccai2018.org/en/",
  approx: 0,
});
deadlines.push({
  venue: "ICML",
  area: "Machine Learning",
  deadline: moment("2019-01-18 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://icml.cc",
  approx: 0,
});
deadlines.push({
  venue: "SysML",
  area: "Machine Learning",
  deadline: moment("2018-09-28 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://sysml.cc",
  approx: 0,
});
deadlines.push({
  venue: "UAI",
  area: "Machine Learning",
  deadline: moment("2018-03-09 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://www.auai.org/uai2018/index.php",
  approx: 0,
});
deadlines.push({
  venue: "NIPS",
  area: "Machine Learning",
  deadline: moment("2018-05-18 20:00:00 -0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "https://nips.cc/",
  approx: 0,
});
deadlines.push({
  venue: "AISTATS",
  area: "Machine Learning",
  deadline: moment("2018-10-04 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://www.aistats.org/",
  approx: 0,
});
deadlines.push({
  venue: "ICLR",
  area: "Machine Learning",
  deadline: moment("2018-09-27 14:00:00 -0700", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://www.iclr.cc",
  approx: 0,
});
deadlines.push({
  venue: "SODA",
  area: "Algorithms",
  deadline: moment("2018-07-05 16:59:00 -0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://www.siam.org/meetings/da19/",
  approx: 0,
});
deadlines.push({
  venue: "ACL",
  area: "Linguistics",
  deadline: moment("2018-02-22 23:59:00 -1100", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://acl2018.org/",
  approx: 0,
})
deadlines.push({
  venue: "WABI",
  area: "Algorithms",
  deadline: moment("2018-05-04 23:59:00 -1100", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://algo2018.hiit.fi/wabi",
  approx: 0,
});
deadlines.push({
  venue: "AAAI",
  area: "AI",
  deadline: moment("2018-09-05 23:59:00 -1000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "https://aaai.org/Conferences/AAAI-19/",
  approx: 0,
});
deadlines.push({
  venue: "KDD",
  area: "AI",
  deadline: moment("2019-02-03 23:59:00 -0800", "YYYY-MM-DD HH:mm:ss Z"),
  website: "https://www.kdd.org/kdd2019",
  approx: 0,
});
deadlines.push({
  venue: "RECOMB",
  area: "Computational Biology",
  deadline: moment("2018-10-30 17:00:00 -0400", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://recomb2019.org/key-dates/",
  approx: 0
});
deadlines.push({
  venue: "APBC",
  area: "Computational Biology",
  deadline: moment("2018-07-30 00:00:00 -0800", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://glab.hzau.edu.cn/APBC2019/",
  approx: 0,
});
deadlines.push({
  venue: "ISMB",
  area: "Computational Biology",
  deadline: moment("2018-01-29 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "https://www.iscb.org/ismb2018",
  approx: 0,
});
deadlines.push({
  venue: "PSB",
  area: "Computational Biology",
  deadline: moment("2018-08-06 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://psb.stanford.edu/",
  approx: 0,
});
deadlines.push({
  venue: "COLING",
  area: "Linguistics",
  deadline: moment("2018-03-16 23:59:00 +0000", "YYYY-MM-DD HH:mm:ss Z"),
  website: "http://coling2018.org/final-call-for-papers/",
  approx: 0,
});

// HELPER FUNCTIONS
var timeDescription = function(x) {
  return x.format("MM/DD/YYYY h:mm:ss A");
}

var timeLeftDescription = function(t) {
  if(t<0) t=0;
  var tseconds = t / 1000;
  var seconds = Math.floor(tseconds) % 60;
  var tminutes = tseconds / 60;
  var minutes = Math.floor(tminutes) % 60;
  var thours = tminutes / 60;
  var hours = Math.floor(thours) % 24;
  var tdays = thours / 24;
  var days = Math.floor(tdays);
  return days + " days, " + hours + "h " + minutes + "m " + seconds + "s";
}

// Display function, called every second or so
function refreshDisplay() {
  var d = moment();
  $("#currtime").text("Current time: " + timeDescription(d));

  // calculate and display deadlines
  for(var i=0;i<deadlines.length;i++) {
    var dl= deadlines[i];
    //if (shouldDisplay[dl.area]) {
    var checkBox = document.getElementById(dl.area);
    if (checkBox.checked == true) {
      var timeLeft= dl.deadline - d;
      warningString= "";
      //if (timeLeft < 0) { warningString= "based on previous year!"; }
      if (dl.approx) { warningString= "based on previous year!"; }
      prefix = "";
      suffix = "";
      if ("website" in dl) {
        prefix = "<a class=\"sd\" href=\"" + dl.website + "\">";
        suffix = "</a>";
      }

      $("#deadline" + i).html(
        prefix + "<div class=\"tld\">" + timeLeftDescription(timeLeft) + "</div>"
               + "<div class=\"vd\">" + dl.venue + "</div>"
               + "<div class=\"ad\">" + dl.area + "</div>"
               + "<div class=\"td\">Deadline: " + timeDescription(dl.deadline) + "</div>"
               + "<div class=\"wd\">" + warningString + "</div>"
               + suffix
      );
      $("#deadline" + i).show();
    } else {
      $("#deadline" + i).hide();
    }
  }
}
// int main(){}
$(document).ready(function() {
  for (var i=0; i<deadlines.length;i++) {
    var d = moment();
    var dl = deadlines[i];
    if (dl.deadline - d <= 0) {
      dl.deadline.add(1, 'year');
      dl.approx = 1;
    }
  }
  deadlines.sort(function(a, b) {
    return a.deadline - b.deadline;
  });
  // create divs for all deadlines and insert into DOM
  for(var i=0;i<deadlines.length;i++) {
    /*var d = moment();
    var dl = deadlines[i];
    var timeLeft = dl.deadline - d;
    if (timeLeft <= 0){
      continue;
    }*/
    $("<div class=dd id=deadline" + i + "></div>").appendTo("div#deadlinesdiv");
    var divid = "#deadline" + i;

    $(divid).hide();
    $(divid).fadeIn(100*(i+1), function() { }); // create a nice fade in effect
  }

  // set up deadline timer to redraw
  setInterval(
    function(){ refreshDisplay(); },
    1000
  );

  // draw!
  refreshDisplay();
});
/*
function toggleML {
  shouldDisplay["Machine Learning"] = !shouldDisplay["Machine Learning"];
}
function toggleAI {
  shouldDisplay["AI"] = !shouldDisplay["AI"];
}
function toggleAlg {
  shouldDisplay["Algorithms"] = !shouldDisplay["Algorithms"];
}
function toggleCB {
  shouldDisplay["Computational Biology"] = !shouldDisplay["Computational Biology"];
}
function toggleLin {
  shouldDisplay["Linguistics"] = !shouldDisplay["Linguistics"];
}*/
</script>
