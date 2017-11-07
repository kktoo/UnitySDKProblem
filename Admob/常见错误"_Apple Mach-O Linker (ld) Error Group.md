## xcode8下，接入Admob，导入FrameWork后，出现大量编译错误：

"_OBJC_CLASS_$_MPVolumeView", referenced from:
      objc-class-ref in GoogleMobileAds(flat-arm64)
  "_CMTimeMakeWithSeconds", referenced from:
      l15775 in GoogleMobileAds(flat-arm64)
  "_CMTimeRangeGetEnd", referenced from:
      l15584 in GoogleMobileAds(flat-arm64)
      l15778 in GoogleMobileAds(flat-arm64)
  "_kCMTimeZero", referenced from:
      l15549 in GoogleMobileAds(flat-arm64)
      l15584 in GoogleMobileAds(flat-arm64)
      l15773 in GoogleMobileAds(flat-arm64)
      l15778 in GoogleMobileAds(flat-arm64)
  "_CMTimeCompare", referenced from:
      l15549 in GoogleMobileAds(flat-arm64)
      l15584 in GoogleMobileAds(flat-arm64)
      l15778 in GoogleMobileAds(flat-arm64)
  "_OBJC_CLASS_$_MFMessageComposeViewController", referenced from:
      objc-class-ref in GoogleMobileAds(flat-arm64)
  "_OBJC_CLASS_$_CMMotionManager", referenced from:
      objc-class-ref in GoogleMobileAds(flat-arm64)
  "_CMTimeMake", referenced from:
      l15548 in GoogleMobileAds(flat-arm64)
      l15792 in GoogleMobileAds(flat-arm64)
  "_CMTimeSubtract", referenced from:
      l15778 in GoogleMobileAds(flat-arm64)
  "_CMTimeGetSeconds", referenced from:
      l15584 in GoogleMobileAds(flat-arm64)
      l15752 in GoogleMobileAds(flat-arm64)
      l15778 in GoogleMobileAds(flat-arm64)
      l15803 in GoogleMobileAds(flat-arm64)
      l15804 in GoogleMobileAds(flat-arm64)

## 原因是除了加入sdk的FrameWork之外，还需要加入其他FrameWork，详情如下：

framework名称	缺少会报的错误

### GLKit.framework
_OBJC_CLASS_$_GLKView
_GLKMatrix4Identity

### MobileCoreServices.framework
_kUTTagClassMIMEType
_UTTypeCreatePreferredIdentifierForTag

### CoreVideo.framework
_CVOpenGLESTextureCacheCreateTextureFromImage
_CVOpenGLESTextureGetName
_CVOpenGLESTextureCacheCreate
_CVOpenGLESTextureCacheFlush
_CVPixelBufferGetWidth
_CVOpenGLESTextureGetTarget
_kCVPixelBufferPixelFormatTypeKey
_kCVImageBufferYCbCrMatrix_ITU_R_601_4
_CVPixelBufferGetHeight
_CVBufferGetAttachment
_kCVImageBufferYCbCrMatrixKey

### StoreKit.framework
_OBJC_CLASS_$_SKProductsRequest
_OBJC_CLASS_$_SKMutablePayment
_OBJC_CLASS_$_SKPaymentQueue
_OBJC_CLASS_$_SKStoreProductViewController
_SKStoreProductParameterITunesItemIdentifier

### MediaPlayer.framework
_MPMoviePlayerPlaybackDidFinishNotification
_MPMoviePlayerPlaybackStateDidChangeNotification
_OBJC_CLASS_$_MPMoviePlayerController
_OBJC_CLASS_$_MPVolumeView

### SafariServices.framework
_OBJC_CLASS_$_SFSafariViewController

### AdSupport.framework
_OBJC_CLASS_$_ASIdentifierManager

### CoreMotion.framework
_OBJC_CLASS_$_CMMotionManager

### CoreTelephony.framework
_CTRadioAccessTechnologyDidChangeNotification
_OBJC_CLASS_$_CTTelephonyNetworkInfo

### MessageUI.framework
_OBJC_CLASS_$_MFMailComposeViewController
_OBJC_CLASS_$_MFMessageComposeViewController
### CoreText.framework
_CTFramesetterCreateWithAttributedString
_CTFramesetterSuggestFrameSizeWithConstraints

### GameKit.framework
_OBJC_CLASS_$_GKAchievement
_OBJC_CLASS_$_GKScore
_OBJC_CLASS_$_GKGameCenterViewController
_OBJC_CLASS_$_GKLocalPlayer

### SystemConfiguration.framework
_SCNetworkReachabilityCreateWithAddress
_SCNetworkReachabilityGetFlags
_SCNetworkReachabilityCreateWithName
_SCNetworkReachabilitySetDispatchQueue
_SCNetworkReachabilitySetCallback

### Security.framework
_SecCertificateCreateWithData
_SecTrustCopyExceptions
_SecTrustEvaluate
_SecTrustSetAnchorCertificates
_SecTrustSetExceptions

### CoreMedia.framework
_CMTimeGetSeconds
_CMTimeMakeWithSeconds
_CMTimeMake
_kCMTimeZero

### OpenGLES.framework
_OBJC_CLASS_$_EAGLContext
_glActiveTexture
 
### CFNetwork.framework
_CFHostCreateWithName
_CFHostStartInfoResolution
_CFHostGetAddressing
