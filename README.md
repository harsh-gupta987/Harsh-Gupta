function distanceIsland(map) {
  if (map.length === 0 || map[0].length === 0){
   return 0;
  }

  const rows = map.length;
  const cols = map[0].length;
  let count = 0;

  function deapth(i, j) {
      if (i < 0 || i >= rows || j < 0 || j >= cols || map[i][j] === 'W') return;
      
      map[i][j] = 'W';
      
      deapth(i + 1, j);
      deapth(i - 1, j); 
      deapth(i, j + 1); 
      deapth(i, j - 1);
  }

   for (let i = 0; i < rows; i++) {
      for (let j = 0; j < cols; j++) {
          if (map[i][j] === 'L') {
              count++;
              deapth(i, j);
          }
      }
  }

  return count;
}
const map1 = [
  ["L","L","L","L","W"],
  ["L","L","W","L","W"],
  ["L","L","W","W","W"],
  ["W","W","W","W","W"],
];

const map2 = [
  [
    ["L","L","W","W","W"],
    ["L","L","W","W","W"],
    ["W","W","L","W","W"],
    ["W","W","W","L","L"],
]
]
