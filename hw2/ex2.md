# Ex1

 Tìm hiểu hàm **fs.writeFile** của module FileSystem. Sử dụng fs.writeFile để tạo ra file numbers.txt với nội dung 1 8 5 7 2

----------------------------------------------------------------
**Bài làm**


        const fs = require('fs');

        fs.writeFile('numbers.txt', '1 8 5 7 2', (err) => {
            if(err) throw err;
                console.log(err);
            })


----------------------------------------------------------------
# Ex3

Từ file numbers.txt của Ex1, sử dụng module file system để đọc nội dung, đếm số các sổ lẻ và ghi nội dung vào file result.txt

Ví dụ

file numbers.txt là 1 8 5 7 2 thì file result.txt là 3
file numbers.txt là 9 2 1 3 5 thì file result.txt là 4

-------------

**Bài làm**


        const fs = require('fs');
        fs.readFile('numbers.txt', 'utf8', (err, data) => {
            const oddNumbers = [];
            if (err) {
                console.log(err);
            } else {
                for (let i = 0; i < data.length; i++) {
                    if (data[i] % 2 !== 0) {
                        oddNumbers.push(data[i]);
                    }
                }
                fs.writeFile('result.txt', JSON.stringify(oddNumbers.length), (err) => {
                    if(err) throw err;
                    console.log(err);
                });
            }
        })

----------------------------------------------------------------
# Ex4
Cho đoạn code sau:

        async function wait() {

        }

        async function go() {
        console.log('Starting');
        await wait(2000);
        console.log('running');
        await wait(200);
        console.log('ending');
        }
Hoàn thiện hàm wait sao cho "ending" hiên thị sau "running" 200ms, "running" hiện thị sau "Starting" 2000ms

----------------------------------------------------------------
**Bài làm**

        async function wait(time) {
            await new Promise((resolve) => {
                return setTimeout(resolve, time);
            })
        }

        async function go() {
        console.log('Starting');
        await wait(2000);
        console.log('running');
        await wait(200);
        console.log('ending');
        }

        go();