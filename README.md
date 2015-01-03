# git-notes-test

> Testing out the
> [git-notes](https://www.kernel.org/pub/software/scm/git/docs/git-notes.html)
> command.

Some further reading on the `git-notes` command:

- [Note to Self](http://git-scm.com/blog/2010/08/25/notes.html)
- [Git Tip of the Week: Git Notes](http://alblue.bandlem.com/2011/11/git-tip-of-week-git-notes.html)
- [More Uses for Git Notes](http://blog.adamspiers.org/2013/10/02/more-uses-for-git-notes/)

<div data-height="268" data-theme-id="0" data-slug-hash="EaNXEX" data-default-tab="js" data-user="jbranchaud" class='codepen'><pre><code>// Insertion Sort
//
// Use the Insertion Sort (http://en.wikipedia.org/wiki/Insertion_sort)
// algorithm to sort an array of items.

// swap what is stored at position i and j in the array
function swap(array, i, j) {
  var temp = array[i];
  array[i] = array[j];
  array[j] = temp;
}

// swap what is stored at position i and j in a deep copy of the array
function fswap(array, i, j) {
  var array_copy = array.map(function(value) { return value; }),
      temp = array_copy[i];
  array_copy[i] = array_copy[j];
  array_copy[j] = temp;
  return array_copy;
}

// given the position of an item in the array, this function starts at the
// beginning of the array and iterates forward until it finds the position
// where it can insert the item - that is, when an item bigger than the
// current item is encountered.
function insert(array, i) {
  for( var j = 0; j &lt; i; j++ ) {
    if( array[j] &gt; array[i] ) {
      var temp = array[i];
      // go from position i down to j, shifting the items to the right
      for( var k = i; k &gt; j; k-- ) {
        swap(array, k, k-1);
      }
      // insertion of i happens during the swapping
      break;
    }
  }
}

// sort each element in the array using the insert function
function sort(array) {
  array = array || [];
  for( var i = 0; i &lt; array.length; i++ ) {
    insert(array, i);
  }
  return array;
}

console.log(&quot;[] -&gt; &quot; + sort([]));
console.log(&quot;[5,4,3,2,1] -&gt; &quot; + sort([5,4,3,2,1]));
console.log(&quot;[7,3,5,9,1,4,2,0,8] -&gt; &quot; + sort([7,3,5,9,1,4,2,0,8]));</code></pre>
<p>See the Pen <a href='http://codepen.io/jbranchaud/pen/EaNXEX/'>Insertion Sort</a> by Josh Branchaud (<a href='http://codepen.io/jbranchaud'>@jbranchaud</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
</div><script async src="//assets.codepen.io/assets/embed/ei.js"></script>

## CodePen with an iframe

<iframe height='350' scrolling='no' src='//codepen.io/jbranchaud/embed/EaNXEX/' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/jbranchaud/pen/EaNXEX/'>Insertion Sort</a> by Josh Branchaud (<a href='http://codepen.io/jbranchaud'>@jbranchaud</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>
