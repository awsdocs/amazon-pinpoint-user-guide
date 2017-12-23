# Managing Mobile Push Channels with Amazon Pinpoint<a name="channels-mobile-manage"></a>

Using the console, you can update the credentials that allow Amazon Pinpoint to send push notifications to iOS and Android devices\. You can provide credentials for the following push notification services, each of which is supported by an Amazon Pinpoint channel: 

+ Firebase Cloud Messaging \(FCM\) or its predecessor, Google Cloud Messaging \(GCM\)\.

+ Apple Push Notification service \(APNs\)\.

+ Baidu Cloud Push\.

+ Amazon Device Messaging \(ADM\)\.

For FCM, GCM, and APNs, you initially provide your credentials when you add your app as a mobile project in AWS Mobile Hub\. For Baidu and ADM, you can provide your credentials only in the Amazon Pinpoint console\.

**To update mobile push settings**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project for which you want to manage mobile push settings\.

1. In the navigation menu, choose **Settings**\.

1. On the **Settings** page, choose **Channels**, and choose **Mobile Push**\.

1. Under **Choose the push notification services that you want to enable**, you can update your credentials for the following services:

   + **FCM/GCM** – Requires an API key \(also referred to as a server key\), which you get from the Firebase console or the Google API console\. For more information about getting FCM credentials, see [Credentials](https://firebase.google.com/docs/cloud-messaging/concept-options#credentials) in the Firebase documentation\.

   + **APNs** – Requires an authentication token signing key or a TLS certificate, which you get from your Apple developer account\. For more information, see the *Managing APNs Settings* section\.

   + **Baidu** – Requires an API key and a secret key, which you get from your Baidu Cloud Push project\.

   + **ADM** – Requires the OAuth Credentials \(Client ID and Client Secret\) from your Amazon Developer account\. For more information, see [Obtaining Amazon Device Messaging Credentials](https://developer.amazon.com/public/apis/engage/device-messaging/tech-docs/adm-obtaining-credentials) in the Amazon Developer documentation\.

1. When you finish, choose **Save**\.

## Managing APNs Settings<a name="channels-mobile-manage-apns"></a>

On the **Settings** page, for **APNs**, you can authorize Amazon Pinpoint to send push notifications to your iOS app by providing information about your APNs *key* or *certificate*:

**Key**  
A private signing key used by Amazon Pinpoint to cryptographically sign APNs authentication tokens\. You obtain the signing key from your Apple developer account\.   
If you provide a signing key, Amazon Pinpoint uses a token to authenticate with APNs for every push notification that you send\. With your signing key, you can send push notifications to APNs production and sandbox environments\.  
Unlike certificates, your signing key does not expire\. You only provide your key once, and you don't need to renew it later\. You can use the same signing key for multiple apps\. For more information, see [Communicate with APNs using authentication tokens](http://help.apple.com/xcode/mac/current/#/dev54d690a66) in *Xcode Help*\.

**Certificate**  
A TLS certificate that Amazon Pinpoint uses to authenticate with APNs when you send push notifications\. An APNs certificate can support both production and sandbox environments, or it can support only the sandbox environment\. You obtain the certificate from your Apple developer account\.   
A certificate expires after one year\. When this happens, you must create a new certificate, which you then provide to Amazon Pinpoint to renew push notification deliveries\. For more information, see [Communicate with APNs using a TLS certificate](http://help.apple.com/xcode/mac/current/#/dev11b059073) in *Xcode Help*\.

**To manage APNs settings**

1. For **Default authentication type**, choose whether Amazon Pinpoint authenticates with APNs using your signing **key** or your TLS **certificate**\. Amazon Pinpoint uses this default for every APNs push notification that you send using the console\. You can override the default when you send a message programmatically using the Amazon Pinpoint API, the AWS CLI, or an AWS SDK\. If your default authentication type fails, Amazon Pinpoint does not attempt to use the other authentication type\.

1. For **Authentication type**, choose **Key** or **Certificate** to manage the settings for that type\.

   + For **Key**, provide the following information from your Apple developer account at [https://developer.apple.com/account/](https://developer.apple.com/account/)\. Amazon Pinpoint requires this information to construct authentication tokens\.

     + **Key ID** – The ID assigned to your signing key\. To find this value, choose **Certificates, IDs & Profiles**, and choose your key in the **Keys** section\.

     + **Bundle identifier** – The ID assigned to your iOS app\. To find this value, choose **Certificates, IDs & Profiles**, choose **App IDs** in the **Identifiers** section, and choose your app\.

     + **Team ID** – The ID assigned to your Apple developer account team\. This value is provided on the **Membership** page\.

     + **Authentication key** – The \.p8 file that you download from your Apple developer account when you create an authentication key\. Apple allows you to download your authentication key only once\.

   + For **Certificate**, provide the following information:

     + **SSL certificate** – The \.p12 file for your TLS certificate\. You can export this file from Keychain Access after you download and install your certificate from your Apple developer account\.

     + **Certificate password** – If you assigned a password to your certificate, specify it here\.

1. If your certificate supports sending push notifications to the APNs production environment, enable **certificate supports production environment**\. Do not enable this option if your certificate supports only the sandbox environment\.

1. When you finish, choose **Save**\.