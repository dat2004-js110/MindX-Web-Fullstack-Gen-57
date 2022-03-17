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