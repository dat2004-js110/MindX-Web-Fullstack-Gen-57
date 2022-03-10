
Ex: 1_Cho đoạn code sau

        const obj1 = { x: 20, y: 30 };

        function cloneDeep(obj) {

        }
        const obj2 = cloneDeep(obj1)
        obj2.x = 10

        Hoàn thiện function cloneDeep sao cho sau khi thực hiện chương trình

        obj1 = { x: 20, y: 30 }
        obj2 = { x: 10, y: 30 }
        const obj1 = { x: 20, y: 30 };

------------
**Bài làm:**
------------


        const obj1 = { x: 20, y: 30 };

        function cloneDeep(obj) {
        return {...obj}
        };
        const obj2 = cloneDeep(obj1);
        obj2.x = 10;

        console.log(obj1);
        console.log(obj2);
        

Ex 2:


        
        const macbooks = ['macbook2015', { model: 'macbook2014' }, 'macbook2017'];
        const apples = [...macbooks];
        apples[0] = 'air';
        apples[1].model = 'm1';

        console.log(macbooks) // ["macbook2015",{model: 'm1'}
        ,"macbook2017"];
        console.log(apples) // ["air",{model: 'm1'}
        ,"macbook2017"];
        

-----


giải thích: 

- apples clone hoàn toàn của macbooks
- macbooks[0] và macbook[2] là kiểu string(nguyên thủy) nên khi thay đổi giá trị của apples thì không ảnh hưởng gì đến macbooks
- macbook[1] là kiểu object nên khi ta clone thì macbook[1] và apples[1] vẫn trỏ cùng đến 1 bộ nhớ nên giá trị của cả 2 cùng bị thay đổi cùng nhau
            
--------------------------------------------------------
Ex 3: 
 -   Kết quả in ra là **undefined**. Lý do là **hoisting**. Trong hàm show() thì biến text được khai báo mà không gán dữ liệu thì mặc định nó có giá trị là undefined. Biến text bên ngoài hàm show() là biến global, có scope được ưu tiên sau biến text nằm trong hàm. Còn xét trong hàm show(), hoisting nên var text có giá trị khởi tạo là undefined => console.log(text) = undefined.     
        

Ex 5: 
- Hàm **Counter()** được thực thi với toán tử new và gán cho biến counter. Các bước sẽ xảy ra là:
- Một đối tượng trống mới được tạo và gán cho **this**.
- Các phần thân hàm được thực thi. Thêm method **up** và **down** cho **this**.
- Giá trị của this được return cho biến counter.
- Do giá trị được return trở lại biến counter nên sau **counter.up()** lần thứ 1 thì count = 1, value count lưu lại trong counter. Sau khi **counter.up()** lần thứ 2 thì count = 2. Sau khi **counter.down() thì count = 1.**

Ex 6: 
- màn hình sẽ hiện ra theo thứ tự là: 
     **hello hi world**
- do cơ chế của hàm settimeout Do đó có rất nhiều hạn chế khi ta dùng hàm settimeout, hoặc onclick,vvv vì khi như thế nó phải chờ hàm settimeout chạy xong thì đoạn code đằng sau mới chạy được.
  
       