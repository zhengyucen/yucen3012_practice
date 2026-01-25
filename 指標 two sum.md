## 指標
### 指標應用1

'''
void swap_bad(int x, int y) {
    int temp = x;
    x = y;
    y = temp;
    // 在這裡 x 和 y 確實交換了，但它們只是複製品
}

int main() {
    int a = 10;
    int b = 20;
    
    swap_bad(a, b); 
    
    // 結果：a 還是 10, b 還是 20
    // 交換失敗！因為函數裡改的只是複製品。
}'''
