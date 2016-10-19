# 仿简书富文本编辑器实现
支持富文本编辑，包括文本的加粗，斜体，块引用等等，还可以插入链接，图片和分割线等。

WebViewj初始化，加载本地Html文件

  
    private static final String SETUP_HTML = "file:///android_asset/editor.html";
    private static final String CALLBACK_SCHEME = "re-callback://";
    private static final String STATE_SCHEME = "re-state://";
    private boolean isReady = false;
    private String mContents;
    private OnTextChangeListener mTextChangeListener;
    private OnDecorationStateListener mDecorationStateListener;
    private AfterInitialLoadListener mLoadListener;
    private OnScrollChangedCallback mOnScrollChangedCallback;

    public RichEditor(Context context) {
        this(context, null);
    }

    public RichEditor(Context context, AttributeSet attrs) {
        this(context, attrs, android.R.attr.webViewStyle);
    }

    @SuppressLint("SetJavaScriptEnabled")
    public RichEditor(Context context, AttributeSet attrs, int defStyleAttr) {
        super(context, attrs, defStyleAttr);

        setVerticalScrollBarEnabled(false);
        setHorizontalScrollBarEnabled(false);
        getSettings().setJavaScriptEnabled(true);
        setWebChromeClient(new WebChromeClient());
        setWebViewClient(createWebviewClient());
        loadUrl(SETUP_HTML);

        applyAttributes(context, attrs);
    }
    
   [!image](image_warehouse/捕获4.PNG)
   [!image](image_warehouse/捕获.PNG)
   [!image](image_warehouse/捕获1.PNG)
   [!image](image_warehouse/捕获2.PNG)
    
    最终效果展示：
    
    
   
