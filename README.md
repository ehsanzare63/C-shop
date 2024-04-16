# C-shop
خوب، در ابتدا باید یک ساختار پایه برنامه‌ی شاپتان را با زبان C++ ایجاد کنیم. در زیر چند قطعه کد C++ برای شما آماده کرده‌ام که یک ساختار ابتدایی برای برنامه‌ی شاپ آنلاین شما می‌باشد. این کدها تنها نقطه شروعی هستند و شما می‌توانید آن‌ها را به مرور گسترش دهید:

### ۱. ساختار کلاس برای کالا
#include <iostream>
#include <string>

class Product {
public:
    std::string name;
    double price;

    Product(std::string n, double p) : name(n), price(p) {}
    
    void displayProductDetails() {
        std::cout << "Product Name: " << name << std::endl;
        std::cout << "Price: $" << price << std::endl;
    }
};


### ۲. ساختار کلاس برای فروشگاه آنلاین
#include <iostream>
#include <vector>
#include "Product.h" // Include the Product class header file

class OnlineStore {
public:
    std::vector<Product> products;

    void addProduct(Product product) {
        products.push_back(product);
    }

    void displayAllProducts() {
        for (const Product& product : products) {
            product.displayProductDetails();
            std::cout << "-----------------" << std::endl;
        }
    }
};


### ۳. نمونه استفاده از کد
#include <iostream>
#include "Product.h"
#include "OnlineStore.h"

int main() {
    OnlineStore store;

    Product p1("Laptop", 1200);
    Product p2("Smartphone", 800);
    
    store.addProduct(p1);
    store.addProduct(p2);

    store.displayAllProducts();

    return 0;
}


این کدها بر مبنای ساختار مدل کالا و فروشگاه آنلاین ساخته شده‌اند. می‌توانید این ساختار را گسترش داده و ویژگی‌های دیگری مانند مدیریت کاربران، سبد خرید، پرداخت آنلاین و ... استفاده کنید 
