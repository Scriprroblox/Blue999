  Future<String> saveImage(Uint8List image) async {
    var response =
        await ImageGallerySaver.saveImage(image, isReturnImagePathOfIOS: true);
    if (Platform.isAndroid) {
      return response['filePath'].toString();
    } else {
      return response['filePath'].toString().replaceAll(RegExp('file://'), '');
    }
  }# Blue999
