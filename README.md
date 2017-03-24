# play-tetris-shape-anastomosis

	function playtetris (board, Block) {

		//var	block		= blockWrapper(inputBlock),
		var	boardRows	= board.length,
			boardCols	= board[0].length,
			blockRows	= block.length,
			blockCols	= block[0].length,
			blockSize	= blockRows*blockCols,
			counter  	= 0,
			flag	 	= true;

		for (var i = 0; i < (boardRows - blockRows); i++) {
			for (var j = 0; j < (boardCols - blockCols); j++) {
				counter = 0;
				for (var k = 0; k < blockRows; k++) {
					for (var l = 0; l < blockCols; l++) {
						if (block[k][l] === board[i+k][j+l]) counter++
					}
				};
				if (counter === blockSize) {
					if (i <> 0) && (j <> 0) {
						if (board[i-1][j-1] <> "■") flag = false
					};
					if (i <> 0) && ((j + blockCols - 1) <> (boardCols - 1)) {
						if (board[i-1][j+blockCols] <> "■") flag = false
					};
					if ((i + blockRows - 1) <> (boardRows - 1)) && (j <> 0) {
						if (board[i+blockRows][j-1] <> "■") flag = false
					};
					if ((i + blockRows - 1) <> (boardRows - 1)) && ((j + blockCols - 1) <> (boardCols - 1)) {
						if (board[i+blockRows][j+blockCols] <> "■") flag = false
					};
					if (i <> 0) {
						for (var count = i; count < ; ) {
							if (condition) flag = false
						}
					};
					if (j <> 0) {
					};
					if (i + blockRows <> boardRows) {
					};
					if (j + blockCols <> boardCols) {
					};
					if flag return stringCreator (i,j,k,l,block)
				}
			}
		}

		return ""
	};

	function stringCreator (i,j,k,l,block) {

		var res = [];

		for (var c1 = 0; c1 < k; c1++) {
			for (var c2 = 0; c2 < l; c2++) {
				if (block[c1][c2] === "□") res.push(`[${i+c1},${j+c2}]`)
			}
		} 

		return res.join(",");
	};

	function blockWrapper (block) {
		var	res	= [],
			line	= "■".repeat(block[0].length+2).split("");
		res.push(line);
		for (var i = 0; i < block.length; i++) {
			res.push(("■" + block[i].join("") + "■").split(""))
		}
		res.push(line);
		return res
	}
