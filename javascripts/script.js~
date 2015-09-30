(function() {
  $(function() {
    var $oldLine, $word, delay, lastChangeTime, lines, 
    $word = $('#word');
    lines = $.makeArray($word.children());
    $oldLine = null;
    lastChangeTime = null;
    delay = 2000;
    next = function() {
      var $line;
      if (!(lines.length > 0)) {
        return;
      }
      $line = $(lines.shift());
      if ($oldLine) {
        $oldLine.css('opacity', 0);
      }
      $line.css('opacity', 1);
      $oldLine = $line;
      return lastChangeTime = new Date;
    };
    setTimeout(function() {
      next();
      return setInterval(function() {
        if (new Date - lastChangeTime > $oldLine.text().length * 500) {
          return next();
        }
      }, 50);
    }, 100);
    return $word.click(function() {
      if (new Date - lastChangeTime < delay) {
        return;
      }
      return next();
    });
  });

}).call(this);

