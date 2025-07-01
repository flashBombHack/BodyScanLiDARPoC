Apple Object Capture Sample PoC
A Proof-of-Concept (PoC) iOS application demonstrating Apple's Object Capture API for generating high-quality, textured 3D models using photogrammetry on compatible iPhones/iPads.

Project Overview
This project is a direct adaptation of Apple's "Scanning Objects Using Object Capture" sample code from WWDC. It showcases the powerful capabilities of Object Capture to create visually rich 3D models from a series of photographs, enhanced by LiDAR data for accurate scale and geometry.

The primary goal of this PoC is to demonstrate the feasibility of acquiring refined 3D assets that can serve as input for advanced backend processing, such as AI-driven body measurement analysis.

Features
High-Quality 3D Model Generation: Utilizes Apple's Object Capture API (photogrammetry) to create detailed, textured 3D models from captured images.

Guided Capture Workflow: Provides on-screen instructions to guide the user through the process of taking photos from various angles for optimal reconstruction.

USDZ Export: Generates industry-standard .usdz (Universal Scene Description Zip) files, which are single, self-contained bundles containing mesh, materials, and textures.

File Sharing: Integrates a standard iOS share sheet for easy transfer of the .usdz file (e.g., AirDrop, Save to Files, Email).

Real-time Preview: Offers a live visual preview during the capture process to help ensure good coverage.

 Prerequisites
To build and run this project, you will need:

Xcode 16.0 beta or later: This project requires the latest Xcode version that includes the iOS 18 SDK.

Download from Apple Developer Downloads.

macOS Sequoia 15.0 or later: Required for Xcode 16.x compatibility.

iOS Device with LiDAR Scanner:

iPhone 12 Pro / Pro Max, iPhone 13 Pro / Pro Max, iPhone 14 Pro / Pro Max, iPhone 15 Pro / Pro Max.

iPad Pro (2020 or later models).

iOS 18.0 or later: Running on your target device.

Apple Developer Account: A free developer account (associated with your Apple ID) is sufficient for running on your own device.

Getting Started
Follow these steps to clone, build, and run the project:

Clone the Repository:

git clone https://github.com/yourusername/YourRepoName.git
cd YourRepoName # Navigate to the root of your cloned repository

(Replace yourusername with your GitHub username and YourRepoName with your actual repository name, e.g., BodyScanLidarPoC).

Navigate to the Project File:

The .xcodeproj file is nested within a subfolder.

From the root of your cloned repository, navigate into the GuidedCaptureSample folder:

cd GuidedCaptureSample

Now, open the project:

open GuidedCaptureSample.xcodeproj

This will open the project in Xcode.

Configure Signing & Capabilities:

In Xcode's Project Navigator (left sidebar), click on the GuidedCaptureSample project (the very top item).

Under TARGETS, select the GuidedCaptureSample target.

Go to the Signing & Capabilities tab.

Check "Automatically manage signing."

For the "Team" dropdown, select your personal Apple ID or your Apple Developer Program team. If your Apple ID isn't listed, add it via Xcode > Settings... > Accounts.

Xcode will attempt to fix any signing issues.

Set Deployment Target:

While still on the GuidedCaptureSample target, go to the General tab.

In the Deployment Info section, ensure Minimum Deployments is set to iOS 18.0. (This should be available if you're using Xcode 16.0 beta or later).

Select Your Device:

Connect your compatible iPhone/iPad to your Mac via USB.

Unlock your device and tap "Trust This Computer" if prompted.

In Xcode's toolbar (top of the window), use the device selector dropdown to choose your connected iPhone/iPad.

Note: If your device shows as "unavailable" or "iOS [version] not installed," Xcode might be downloading necessary device support files/simulators. Let this download complete before proceeding.

Build and Run:

Click the "Run" button (the solid play button icon) in Xcode's toolbar.

On your iPhone/iPad, grant permissions for Camera Access and Photos Access when prompted.

If you encounter an "Untrusted Developer" alert, go to Settings > General > VPN & Device Management (or Device Management on older iOS versions) on your device, tap on your developer profile, and select "Trust."

 How to Use the Sample App
The app provides on-screen guidance for capturing a 3D model:

Choose an Object: Start with a simple, static, non-reflective object (e.g., a shoe, a small statue, a mug).

Follow On-Screen Guidance: The app will instruct you to move around the object, taking photos from various angles (e.g., low, medium, high). It provides visual feedback on coverage.

Initiate Reconstruction: Once enough data is captured, the app will prompt you to start the 3D model reconstruction process. This is computationally intensive and will run in the background (it may take several minutes depending on the object and device).

View Result & Export: After processing, the app will display the generated 3D model. Look for a share/export button to save the .usdz file.

Viewing the Exported USDZ File
Once you have the .usdz file on your computer, you can view it using:

macOS: Simply double-click the .usdz file. It will open directly in macOS's built-in Preview app.

Windows: Use Microsoft's "3D Viewer" app (available in the Microsoft Store).

Online 3D Viewers (search for "online USDZ viewer"): Many web-based tools now support USDZ for quick viewing.

Note on Body Scanning: While Object Capture can generate high-quality models, scanning a human body for precise measurements presents unique challenges (e.g., subject movement, hair, clothing details). For your PoC, focus on demonstrating the capability of capturing refined 3D assets, acknowledging that further processing and specific scanning techniques would be required for accurate body measurements.

⚠Troubleshooting
"iOS [version] not installed" / Device Unavailable:

Ensure your Xcode version is 16.0 beta or later.

If Xcode is downloading "Simulator iOS [version]," let it complete. This includes necessary device support files for your physical iPhone/iPad.

Build Errors:

Ensure your macOS is Sequoia 15.0 or later.

Confirm your Xcode version is 16.0 beta or later.

Perform a Product > Clean Build Folder in Xcode.

Poor Scan Quality / Artifacts:

For photogrammetry, subject stillness is paramount. Even slight movements can cause distortions.

Ensure even, bright lighting without harsh shadows or glare.

Scan objects with some texture; avoid perfectly plain, reflective, or transparent surfaces.

Follow the app's on-screen guidance for full coverage from all angles.
