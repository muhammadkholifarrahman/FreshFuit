# Fresh Fruit
    Fresh Fruit adalah sebuah aplikasi keranjang buah yang dapat menambah dan menghapus item buah yang kita masukkan kedalam keranjang tersebut


## Fungsinya
- Bisa menambahkan buah kedalam keranjang
- Bisa menghapus buah yang sudah ditambahkan yang di dalam keranjang
- Jika keranjang penuh maka akan ada info buah melebihi batas keranjang


## How Does it Works?

Ada beberapa method yang dipakai pada folder model

```Bucket.cs``` ```BucketEventListener``` ```Fruit.cs``` dan ```Seller.cs```

Untuk menambah dan mengurangi isi keranjang bisa dilakukan pada ```MainWindow.xaml.cs```

```csharp
Seller kholif;
        public MainWindow()
        {
            InitializeComponent();

            Bucket keranjangBuah = new Bucket(2);
            BucketController bucketController = new BucketController(keranjangBuah, this);

            kholif = new Seller("kholif", bucketController);

            listBoxBucket.ItemsSource = keranjangBuah.findAll();
        }
        public void onFailed(string massage)
        {
            MessageBox.Show(massage);
        }
        public void onSucceed(string massage)
        {
            listBoxBucket.Items.Refresh();
        }

        private void OnButtonAddAnggurClicked(object sender, RoutedEventArgs e)
        {
            Fruit anggur = new Fruit("anggur");
            kholif.addFruit(anggur);

            listBoxBucket.Items.Refresh();

        }

        private void OnButtonAddAppleClicked(object sender, RoutedEventArgs e)
        {
            Fruit apple = new Fruit("Apple");
            kholif.addFruit(apple);

            listBoxBucket.Items.Refresh();
        }

        private void OnButtonAddBananaClicked(object sender, RoutedEventArgs e)
        {
            Fruit banana = new Fruit("banana");
            kholif.addFruit(banana);

            listBoxBucket.Items.Refresh();
        }

        private void OnButtonAddOrangeClicked(object sender, RoutedEventArgs e)
        {
            Fruit orange = new Fruit("orange");
            kholif.addFruit(orange);

            listBoxBucket.Items.Refresh();
        }
```