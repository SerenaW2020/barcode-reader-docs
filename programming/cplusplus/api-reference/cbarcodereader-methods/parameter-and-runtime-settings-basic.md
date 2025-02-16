---
layout: default-layout
title: Dynamsoft Barcode Reader C++ API Reference - Basic Settings Methods
description: This page shows basic Runtime Settings methods of Dynamsoft Barcode Reader for C++ Language.
keywords: SetModeArgument, GetModeArgument, GetRuntimeSettings, UpdateRuntimeSettings, ResetRuntimeSettings, Basic Settings Methods, CBarcodeReader, api reference, c++
needAutoGenerateSidebar: true
---


# Basic Settings Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`SetModeArgument`](#setmodeargument) | Set argument value for the specified mode parameter. |
  | [`GetModeArgument`](#getmodeargument) | Get argument value for the specified mode parameter. |
  | [`GetRuntimeSettings`](#getruntimesettings) | Get current runtime settings. |
  | [`UpdateRuntimeSettings`](#updateruntimesettings) | Modify and update the current runtime settings. |
  | [`ResetRuntimeSettings`](#resetruntimesettings) | Reset runtime settings to default. |




  
## SetModeArgument

Set argument value for the specified mode parameter.


```cpp
int dynamsoft::dbr::CBarcodeReader::SetModeArgument (const char* pModesName, const int index, const char* pArgumentName, const char* pArgumentValue, char errorMsgBuffer[] = NULL,  onst int errorMsgBufferLen = 0)	
```   
#### Parameters
`[in]	pModesName` The mode parameter name to set argument.  
`[in]	index` The array index of mode parameter to indicate a specific mode.  
`[in]	pArgumentName` The name of the argument to set.  
`[in]	pArgumentValue` The value of the argument to set.  
`[in,out]	errorMsgBuffer`<sub>Optional</sub> The buffer is allocated by the caller and the recommended length is 256. The error message will be copied to the buffer.  
`[in]	errorMsgBufferLen`<sub>Optional</sub> The length of the allocated buffer.  

#### Return value
Returns error code. Possible return(s): DBR_OK; DBRERR_SET_MODE_ARGUMENT_ERROR.  
*You can call [`GetErrorString`](status-retrieval.md#geterrorstring) to get detailed error message.*

#### Remark
Check follow link for available modes and arguments:
- [`BarcodeColourModes`]({{ site.parameters_reference }}image-parameter/BarcodeColourModes.html#mode-arguments)
- [`BinarizationModes`]({{ site.parameters_reference }}image-parameter/BinarizationModes.html#mode-arguments)
- [`ColourClusteringModes`]({{ site.parameters_reference }}image-parameter/ColourClusteringModes.html#mode-arguments)
- [`ColourConversionModes`]({{ site.parameters_reference }}image-parameter/ColourConversionModes.html#mode-arguments)
- [`DeformationResistingModes`]({{ site.parameters_reference }}image-parameter/DeformationResistingModes.html#mode-arguments)
- [`ImagePreprocessingModes`]({{ site.parameters_reference }}image-parameter/ImagePreprocessingModes.html#mode-arguments)
- [`IntermediateResultSavingMode`]({{ site.parameters_reference }}image-parameter/IntermediateResultSavingMode.html#mode-arguments)
- [`LocalizationModes`]({{ site.parameters_reference }}image-parameter/LocalizationModes.html#mode-arguments)
- [`RegionPredetectionModes`]({{ site.parameters_reference }}image-parameter/RegionPredetectionModes.html#mode-arguments)
- [`ScaleUpModes`]({{ site.parameters_reference }}image-parameter/ScaleUpModes.html#mode-arguments)
- [`TextFilterModes`]({{ site.parameters_reference }}image-parameter/TextFilterModes.html#mode-arguments)
- [`TextureDetectionModes`]({{ site.parameters_reference }}image-parameter/TextureDetectionModes.html#mode-arguments) 

#### Code Snippet
```cpp
CBarcodeReader* reader = new CBarcodeReader();
reader->InitLicense("t0260NwAAAHV***************");
PublicRuntimeSettings* pSettings = new PublicRuntimeSettings;
reader->GetRuntimeSettings(pSettings);
pSettings->binarizationModes[0] = BM_LOCAL_BLOCK;
char errorMessage[256];
reader->UpdateRuntimeSettings(pSettings, errorMessage, 256);
reader->SetModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1", errorMessage, 256);
delete pSettings;
delete reader;
```







## GetModeArgument

Get argument value for the specified mode parameter.

```cpp
int dynamsoft::dbr::CBarcodeReader::GetModeArgument (const char* pModesName, const int index, const char* pArgumentName, char valueBuffer[], const int valueBufferLen, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)	
```   
   
#### Parameters  
`[in]	pModesName` The mode parameter name to get argument.  
`[in]	index` The array index of mode parameter to indicate a specific mode.  
`[in]	pArgumentName` The name of the argument to get.  
`[in,out]	valueBuffer` The buffer is allocated by caller and the recommended length is 480. The argument value would be copied to the buffer.  
`[in]	valueBufferLen` The length of allocated buffer.  
`[in,out]	errorMsgBuffer`<sub>Optional</sub> The buffer is allocated by the caller and the recommended length is 256. The error message will be copied to the buffer.  
`[in]	errorMsgBufferLen`<sub>Optional</sub> The length of the allocated buffer.  

#### Return value
Returns error code. Possible return(s): DBR_OK; DBRERR_GET_MODE_ARGUMENT_ERROR.  
*You can call [`GetErrorString`](status-retrieval.md#geterrorstring) to get detailed error message.*

#### Remark
Check follow link for available modes and arguments:
- [`BarcodeColourModes`]({{ site.parameters_reference }}image-parameter/BarcodeColourModes.html#mode-arguments)
- [`BinarizationModes`]({{ site.parameters_reference }}image-parameter/BinarizationModes.html#mode-arguments)
- [`ColourClusteringModes`]({{ site.parameters_reference }}image-parameter/ColourClusteringModes.html#mode-arguments)
- [`ColourConversionModes`]({{ site.parameters_reference }}image-parameter/ColourConversionModes.html#mode-arguments)
- [`DeformationResistingModes`]({{ site.parameters_reference }}image-parameter/DeformationResistingModes.html#mode-arguments)
- [`ImagePreprocessingModes`]({{ site.parameters_reference }}image-parameter/ImagePreprocessingModes.html#mode-arguments)
- [`IntermediateResultSavingMode`]({{ site.parameters_reference }}image-parameter/IntermediateResultSavingMode.html#mode-arguments)
- [`LocalizationModes`]({{ site.parameters_reference }}image-parameter/LocalizationModes.html#mode-arguments)
- [`RegionPredetectionModes`]({{ site.parameters_reference }}image-parameter/RegionPredetectionModes.html#mode-arguments)
- [`ScaleUpModes`]({{ site.parameters_reference }}image-parameter/ScaleUpModes.html#mode-arguments)
- [`TextFilterModes`]({{ site.parameters_reference }}image-parameter/TextFilterModes.html#mode-arguments)
- [`TextureDetectionModes`]({{ site.parameters_reference }}image-parameter/TextureDetectionModes.html#mode-arguments)   

#### Code Snippet
```cpp
CBarcodeReader* reader = new CBarcodeReader();
reader->InitLicense("t0260NwAAAHV***************");
PublicRuntimeSettings* pSettings = new PublicRuntimeSettings;
reader->GetRuntimeSettings(pSettings);
pSettings->binarizationModes[0] = BM_LOCAL_BLOCK;
char errorMessage[256];
char argumentValue[480];
reader->UpdateRuntimeSettings(pSettings, errorMessage, 256);
reader->SetModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", "1", errorMessage, 256);
reader->GetModeArgument("BinarizationModes", 0, "EnableFillBinaryVacancy", argumentValue, 480, errorMessage, 256);
delete pSettings;
delete reader;
```







## GetRuntimeSettings

Get current settings and save them into a [`PublicRuntimeSettings`]({{ site.structs }}PublicRuntimeSettings.html) struct.

```cpp
int dynamsoft::dbr::CBarcodeReader::GetRuntimeSettings (PublicRuntimeSettings* psettings)	
```   

#### Parameters
`[in,out]	psettings`	The struct of template settings.
 
#### Return value
Returns error code (returns 0 if the function operates successfully).  
*You can call [`GetErrorString`](status-retrieval.md#geterrorstring) to get detailed error message.*

#### Code Snippet
```cpp
CBarcodeReader* reader = new CBarcodeReader();
reader->InitLicense("t0260NwAAAHV***************");
PublicRuntimeSettings* pSettings = new PublicRuntimeSettings;
int errorCode = reader->GetRuntimeSettings(pSettings);
delete pSettings;
delete reader;
```







## UpdateRuntimeSettings

Update runtime settings with a given [`PublicRuntimeSettings`]({{ site.structs }}PublicRuntimeSettings.html) struct.

```cpp
int dynamsoft::dbr::CBarcodeReader::UpdateRuntimeSettings (PublicRuntimeSettings* pSettings, char errorMsgBuffer[] = NULL, const int errorMsgBufferLen = 0)
```   
   
#### Parameters
`[in]	pSettings`	The struct of template settings.  
`[in,out]	errorMsgBuffer`<sub>Optional</sub> The buffer is allocated by caller and the recommended length is 256. The error message will be copied to the buffer.  
`[in]	errorMsgBufferLen`<sub>Optional</sub> The length of the allocated buffer.  
 
#### Return value
Returns error code (returns 0 if the function operates successfully).  
*You can call [`GetErrorString`](status-retrieval.md#geterrorstring) to get detailed error message.*

#### Code Snippet
```cpp
CBarcodeReader* reader = new CBarcodeReader();
reader->InitLicense("t0260NwAAAHV***************");
PublicRuntimeSettings* pSettings = new PublicRuntimeSettings;
int errorCode = reader->GetRuntimeSettings(pSettings);
pSettings->deblurLevel = 9;
char errorMessage[256];
reader->UpdateRuntimeSettings(pSettings, errorMessage, 256);
delete pSettings;
delete reader;
```







## ResetRuntimeSettings

Reset all parameters to default values.

```cpp
int dynamsoft::dbr::CBarcodeReader::ResetRuntimeSettings ()
```   

#### Return value
Returns error code (returns 0 if the function operates successfully).  
*You can call [`GetErrorString`](status-retrieval.md#geterrorstring) to get detailed error message.*

#### Code Snippet
```cpp
CBarcodeReader* reader = new CBarcodeReader();
reader->InitLicense("t0260NwAAAHV***************");
PublicRuntimeSettings* pSettings = new PublicRuntimeSettings;
int errorCode = reader->GetRuntimeSettings(pSettings);
pSettings->deblurLevel = 9;
char errorMessage[256];
reader->UpdateRuntimeSettings(pSettings, errorMessage, 256);
reader->ResetRuntimeSettings();
delete pSettings;
delete reader;
```
