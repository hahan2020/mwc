mwc
===

mwc=my windows component。mfc太复杂了，用着太不爽了，mwc用于替代mfc

# 总体思路
- 参考mvc思想。module离c++语言还是很近的所以mwc不予处理，mwc主要处理controller和view。

# application
关于com
- 引入com后mwc可能会发生天翻地覆的变化，就目前来说，由于我对com的完全不了解，所以也只能这样了。
## application 构成

    app -- *frame -- *(sub)frame
        -- *module
    
所以我将mvc分别对应到module、frame、app中实现。
还要考虑定时器，定时器也应该在app中实现。(也许是因为我搞web比较多，感觉和web框架差不多。)

## application入口/main函数
mwc通过mwcMainApplication类实现应用的入口main函数，用户只需实例化一个mwcMainApplication的实例即可。
类mwcMainApplication 继承自 类mwcApplication。

## module调用


# view
## view 外观
## view 事件
## view 效果

# com

# 程序事例

    class MyFrame extends mwcMainFrame {
       MyButton btn = new MyButton();
       btn.addListener(new Listener(){
          click() {
             System.out.print("hello world");
          }
       });
       this.add(btn, 10, 100);
    }
    class MyApplication extends mwcMainApplication {
       public void init(){
          mainFrame = new MyFrame();
          mainFrame.show();
       }
    }
    int main() {
       MyApplication app = new MyApplication();
    }
