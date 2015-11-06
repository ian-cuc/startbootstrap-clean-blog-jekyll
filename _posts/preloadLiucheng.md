preload 流程

新建pagelist
从jsapi参数中的url,id,title新建出webviewmodel
放到pagelist里面

如果pagelist.size大于0
则调用preload


                    BaseRuntimeFragment existFrag = mAllFrags.get(modelId);
                    if (existFrag != null) {
                        if (mNewBornFragments.contains(existFrag)) {
                            existFrag.handleActivityOnPause();
                        }
                        //TODO:
                        existFrag.handleActivityOnDestroy();
                    }





        bundle.putSerializable(WEBVIEW_MODEL_KEY, webViewModel);


把数据序列化后放到bundle中，当preload则再取出来

Preload具体流程：1.getArguments，2.Initlayout，然后把webview弄出来

go的话就是add进来