###ios常用控件片段
直接拖到Code snippets library.默认放在 ~/Library/Developer/Xcode/UserData/CodeSnippets下。<br/>如果有好的代码片段，可直接拷贝共享。

######1.UILabel
```
UILabel *label = [[UILabel alloc]initWithFrame:CGRectMake(0,0,0,0)];
label.textColor = [UIColor grayColor];
label.font = [UIFont boldSystemFontOfSize:15];
label.textAlignment = NSTextAlignmentCenter;
label.lineBreakMode = NSLineBreakByTruncatingTail;

```
######2.UIButton
```
UIButton *btn = [UIButton buttonWithType: UIButtonTypeRoundedRect];
btn.frame = CGRectMake(0,0,0,0);
[btn setImage:[UIImage imageNamed:@"xx.png"] forState: UIControlStateNormal];
[btn setTitle:@"ss" forState: UIControlStateNormal];
btn.showsTouchWhenHighlighted = YES;
btn.adjustsImageWhenDisabled = NO;
[btn addTarget:self action:@selector(btnClick:) forControlEvents:UIControlEventTouchUpInside];


```
######3.UITextView
```
UITextView *textView = [[UITextView alloc]initWithFrame: CGRectMake(0,0,0,0)];
textView.layer.borderWidth = 1;
textView.layer.borderColor = [UIColor grayColor].CGColor;
textView.layer.cornerRadius = 5;
textView.editable = YES;
textView.dataDetectorTypes = UIDataDetectorTypeAll; // 网址自动加上链接、可设置电话
textView.allowsEditingTextAttributes = YES; //对选中文字进行加粗处理
textView.selectable = NO; //无法被复制

```
######4.UITextField
```
UITextField *textField = [[UITextField alloc]initWithFrame: CGRectMake(0,0,0,0)];
textField.borderStyle = UITextBorderStyleRoundedRect;
textField.placeholder = @"请输入";
textField.adjustsFontSizeToFitWidth = YES;
textField.minimumFontSize = 14;
textField.textAlignment = NSTextAlignmentLeft;//水平对齐
textField.contentVerticalAlignment = UIControlContentVerticalAlignmentTop;//垂直

```
