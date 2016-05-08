########################
各種記法のサンプル
########################

reStructuredText(reST)

#mark

***************
CSSのカスタム
***************

/static 以下にcssファイルを作成（例えばcustom.css)。カスタム用のCSSを記述

conf.pyに以下を追加

:: 

 def setup(app):
     app.add_stylesheet('custom.css')


make htmlでhtmlを生成するとき、*.rstに変更がないファイルは生成対象にならないので、cssを変更しても反映されない。

===========
sample
===========

--------
日本語
--------

#. リストのサンプル１
#. リストのサンプル２
#. サンプル

~~~~~~~~
Table
~~~~~~~~

.. csv-table:: Frozen Delights!
  :header: "Treat", "Quantity", "Description"
  :widths: 15, 10, 60

   "Treat", "Quantity", "Description"
   "Albatross", 2.99, "On a stick!"
   "Crunchy Frog", 1.49, "If we took the bones out, it wouldn't be
   crunchy, now would it?"
   "Gannet Ripple", 1.99, "On a stick!"

::

  .. csv-table:: Frozen Delights!

   "Treat", "Quantity", "Description"
   "Albatross", 2.99, "On a stick!"
   "Crunchy Frog", 1.49, "If we took the bones out, it wouldn't be
   crunchy, now would it?"
   "Gannet Ripple", 1.99, "On a stick!"

.. highlight:: java
 

::

    public void archiveFromDir(String baseDir, String[] targetExtensions,
            String outputFile, boolean recursive) throws IOException {
        // baseDir内のファイル一覧を取得
        Collection<File> listFiles = FileUtils.listFiles(new File(baseDir), targetExtensions, recursive);
        String[] inputFiles = listFiles.stream().map(t -> {
            String p = t.getPath();
            return p.substring(baseDir.length(), p.length());
        }).toArray(count -> {
            return new String[count];
        });

        this.archiveFromFiles(baseDir, inputFiles, outputFile);
    }


テーブルのサンプル

::

  =====  =====  =======
  A      B      A and B
  =====  =====  =======
  False  False  False
  True   False  False
  False  True   False
  True   True   True
  =====  =====  =======


=====  =====  =======
A      B      A and B
=====  =====  =======
False  False  False
True   False  False
False  True   False
True   True   True
=====  =====  =======


警告やノート

 .. warning::

    上記のケースでは、購入者が誤ってブラウザのリロード機能を実行することで、**まったく同じ商品の購入が２回行われてしまうことになる。**
    購入者の操作ミスが原因ではあるが、アプリケーションとして上記の問題が発生しないように制御する事が望ましい。

 .. note::
 
    上記のケースでは、購入者の操作ミスではないため、購入者に対して問題が発生することはない。






