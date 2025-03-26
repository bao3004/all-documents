## CÁCH CÀI TAILWINDCSS V3

## Chuẩn bị

- nodejs
- Extension: Tailwind CSS Intellisense, PostCSS Language Support

## Cài đặt

1. Install tailwind:

   > npm install -D tailwindcss
   > npx tailwindcss init
   > (khởi tạo file tailwin.config.js)

2. Configure your template paths (copy đoạn ở dưới vào content: [] trong file js ở trên)

   > "./public/\*_/_.{html,js}"

3. Add the tailwind directives to your CSS
   create src/tailwind.css and add three lines below to it.

   > @tailwind base;
   > @tailwind components;
   > @tailwind utilities;

4. Start the tailwind CLI build process: (Hệ thống sẽ tạo folder public và css cần thiết trong đó)

   > npx tailwindcss -i ./src/tailwind.css -o ./public/css/tailwind.css --watch

5. Start using Tailwind in HTML:(tạo 1 file index.html trong public và dán link ở dưới vào)

   > <link href="./tailwind.css" rel="stylesheet">

6. Up code lên git
   Tạo 1 file .gitignore và gõ "node_modules"
   Tạo 1 repo trên github và copy đường dẫn
   > git init
   > git remote add https://github.com/bao3004/tailwind-project.git
   > git remote -v
   > git add .
   > git commit -m "Hi"
   > git push origin master

## CÁC LỆNH THƯỜNG DÙNG

1.  Lệnh đơn

    > uppercase: viết hoa hết
    > gap-[number]: khoảng cách giữa các ptu con
    > mx-auto: tự động căn giữa các phần tử bên trong trên trục x (ngang)
    > my-[number]: margin left + right (number: 1px=1 số tăng dần trong tailwind là 4 pixel)
    > inline-block: nằm cùng dòng với phần tử cùng cấp
    > font-[name]: đổi font chữ, name ở đây đã được define ở tailwind.config.js
    > hidden: ẩn (thường kết hợp với screen lg,xl,2xl,...) lg là screen máy tính full HD
    > bg-[url('../img/...')]: link tới background image  
    > text-center: cho các text căn giữa thẻ div
    > leading-[number]: tăng line-height
    > group: bỏ group vào div cha, bỏ group-hover:block vào div con. Con sẽ xuất hiện khi hover vào cha (con phải có hidden)
    > tracking-wider: độ rộng giữa các chữ

2.  Lệnh dài

    > flex flex-row justify-between items-center: xếp các ptu theo chiều ngang, nằm giữa căn đều trái phải, xếp giữa trên dưới
    > basis 1/6: đặt tỉ lệ cho mỗi phần tử con bên trong flex
    > hover:text-gray-500 ease-in duration-100: hiệu ứng trỏ chuột + độ mượt (in/linear/out/in-out) + thời gian effect
    > relative after:absolute after:w-0 after:h-0.5 after:left-0 after:top-1/2 after:bg-gray-800
    > hover:after:w-full after:transition-all after:ease-in-out duration:1000: tạo 1 after có chiều w,h,color và vị trí cắt ngang text khi hover trong 1s
    > bg-[url('../img/coffee-bg.jpg')] bg-cover bg-no-repeat bg-center: căn bức hình ở giữa thẻ div
    > grid grid-flow-col gap-4: lệnh xếp các phần tử con theo hàng/cột, nếu như muốn define mỗi hàng có số phtu con nhất định thì dùng grid-col-[number] thay vì grid-flow-col
    > left-1/2 -translate-x-1/2: căn giữa thẻ div so với thẻ cha theo cột x trong absolute position
    > bg-[url('../img/..')] bg-cover bg-center bg-no-repeat bg-fixed h-[400px]: hiệu ứng parallax (1 background nằm cố định trên màn hình và khi cuộn qua sẽ tạo 1 hiệu ứng vô cùng đẹp mắt)
    > w-[350px] px-6 py-4 bg-inherit border-[1px] border-gray-700
    outline-none text-white leading-5 focus:border-white transition-all duration-500 placeholder:text-xs
    placeholder:uppercase placeholder:tracking-widest placeholder:text-gray-600: hiệu ứng cho ô email

3.  Trick
    > w-[100vw] relative left-[calc(-50vw+50%)]: bỏ đoạn này vào bất kỳ div nào trong 1 div cha bị giới hạn height hoặc width, thì nó sẽ bỏ giới hạn và tràn ra ngoài.

## Lưu ý:

1. Cách thêm font mới vào dự án
   copy mục import của google font -> paste vào đầu file src/tailwind.css
2. Cài "build:css": "tailwindcss -i ./src/tailwind.css -o ./public/css/tailwind.css --watch" bên trong file package.json và khởi chạy mỗi khi mở VSC.