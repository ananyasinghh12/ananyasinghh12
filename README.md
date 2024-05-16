<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Japan Crossword Puzzle</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }
        table {
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        td {
            width: 30px;
            height: 30px;
            border: 1px solid #000;
            text-align: center;
            vertical-align: middle;
            font-size: 20px;
        }
        input {
            width: 100%;
            height: 100%;
            text-align: center;
            font-size: 20px;
            border: none;
            outline: none;
            background-color: #fff;
        }
        .hint {
            margin: 0 20px;
        }
    </style>
</head>
<body>

    <div id="crossword"></div>

    <div class="hint">
        <h3>Hints</h3>
        <p><strong>Across</strong></p>
        <p>1. A famous type of theater known for its elaborate makeup and costumes.</p>
        <p>4. Traditional Japanese garment worn during festivals.</p>
        <p>6. A city famous for its cherry blossoms and historic temples.</p>

        <p><strong>Down</strong></p>
        <p>1. A form of Japanese poetry with a 5-7-5 syllable structure.</p>
        <p>2. A popular Japanese dish consisting of raw fish and rice.</p>
        <p>3. A type of Japanese garden characterized by dry landscapes using rocks and gravel.</p>
        <p>5. Traditional Japanese puppet theater.</p>
    </div>

    <script>
        const crossword = [
            ['K', 'A', 'B', 'U', 'K', 'I', '', '', ''],
            ['A', '', '', '', '', 'I', '', '', ''],
            ['R', '', 'H', 'A', 'I', 'K', 'U', '', ''],
            ['I', '', '', '', '', 'N', '', '', ''],
            ['M', '', '', '', '', 'A', '', '', ''],
            ['O', '', 'S', 'U', 'S', 'H', 'I', '', ''],
            ['N', '', '', '', '', 'A', '', '', ''],
            ['', '', 'R', 'Y', 'U', 'S', 'A', 'N', ''],
            ['', '', '', '', '', 'I', '', '', ''],
            ['', '', '', '', '', 'K', '', '', '']
        ];

        function createCrossword() {
            const table = document.createElement('table');
            for (let i = 0; i < crossword.length; i++) {
                const row = document.createElement('tr');
                for (let j = 0; j < crossword[i].length; j++) {
                    const cell = document.createElement('td');
                    if (crossword[i][j] !== '') {
                        const input = document.createElement('input');
                        input.maxLength = 1;
                        input.dataset.correct = crossword[i][j];
                        cell.appendChild(input);
                    }
                    row.appendChild(cell);
                }
                table.appendChild(row);
            }
            document.getElementById('crossword').appendChild(table);
        }

        function checkAnswers() {
            const inputs = document.querySelectorAll('input');
            inputs.forEach(input => {
                if (input.value.toUpperCase() === input.dataset.correct) {
                    input.style.backgroundColor = '#c8e6c9';
                } else {
                    input.style.backgroundColor = '#ffccbc';
                }
            });
        }

        createCrossword();
    </script>
</body>
</html>

