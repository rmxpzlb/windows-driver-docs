---
title: MPEG1\_A
description: MPEG1\_A
ms.assetid: 2c4d79b7-3331-49f9-a561-6e5b609543df
keywords:
- MPEG1_A restricted profile WDK DirectX VA
ms.author: windowsdriverdev
ms.date: 04/20/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# MPEG1\_A


## <span id="ddk_mpeg1_a_gg"></span><span id="DDK_MPEG1_A_GG"></span>


The MPEG1\_A restricted profile contains a set of features required for support of MPEG-1 video. Support of this profile is required for video accelerator drivers that provide hardware video acceleration capabilities. This set of features is defined by the following set of restrictions:

### <span id="Restrictions_on_DXVA_ConnectMode"></span><span id="restrictions_on_dxva_connectmode"></span><span id="RESTRICTIONS_ON_DXVA_CONNECTMODE"></span>Restrictions on DXVA\_ConnectMode

The following restriction on the [**DXVA\_ConnectMode**](https://msdn.microsoft.com/library/windows/hardware/ff563138) structure applies when the *bDXVA\_Func* variable defined in the **dwFunction** member of the [**DXVA\_ConfigPictureDecode**](https://msdn.microsoft.com/library/windows/hardware/ff563133) structure is equal to 1.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Structure Member</th>
<th align="left">Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>wRestrictedMode</strong></p></td>
<td align="left"><p>DXVA_RESTRICTED_MODE_MPEG1_A</p></td>
</tr>
</tbody>
</table>

 

### <span id="Restrictions_on_DXVA_PictureParameters"></span><span id="restrictions_on_dxva_pictureparameters"></span><span id="RESTRICTIONS_ON_DXVA_PICTUREPARAMETERS"></span>Restrictions on DXVA\_PictureParameters

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Structure Member</th>
<th align="left">Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>BPP</em> variable (defined by adding 1 to <strong>bBPPminus1)</strong></p></td>
<td align="left"><p>Equals 8</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bSecondField</strong></p></td>
<td align="left"><p>Equals zero</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>MacroblockWidthMinus1</strong></p></td>
<td align="left"><p>15</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>MacroblockHeightMinus1</strong></p></td>
<td align="left"><p>15</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>bBlockWidthMinus1</strong></p></td>
<td align="left"><p>7</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bBlockHeightMinus1</strong></p></td>
<td align="left"><p>7</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>bChromaFormat</strong> (4:2:0)</p></td>
<td align="left"><p>1</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bPicStructure</strong></p></td>
<td align="left"><p>3 (frame structured)</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>bRcontrol</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bBidirectionalAveragingMode</strong></p></td>
<td align="left"><p>Zero (MPEG-2 bidirectional averaging)</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>bMVprecisionAndChromaRelation</strong></p></td>
<td align="left"><p>Zero (MPEG-2 half-sample motion)</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bPicExtrapolation</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>bPicDeblocked</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bPic4MVallowed</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>bPicOBMC</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bMV_RPS</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SpecificIDCT</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>bPicScanFixed</strong></p></td>
<td align="left"><p>Zero</p></td>
</tr>
</tbody>
</table>

 

### <span id="Restrictions_on_DXVA_MBctrl_I_HostResidDiff_1__DXVA_MBctrl_I_OffHostIDCT_1__DXVA_MBctrl_P_HostResidDiff_1__and_DXVA_MBctrl_P_OffHostIDCT_1"></span><span id="restrictions_on_dxva_mbctrl_i_hostresiddiff_1__dxva_mbctrl_i_offhostidct_1__dxva_mbctrl_p_hostresiddiff_1__and_dxva_mbctrl_p_offhostidct_1"></span><span id="RESTRICTIONS_ON_DXVA_MBCTRL_I_HOSTRESIDDIFF_1__DXVA_MBCTRL_I_OFFHOSTIDCT_1__DXVA_MBCTRL_P_HOSTRESIDDIFF_1__AND_DXVA_MBCTRL_P_OFFHOSTIDCT_1"></span>Restrictions on DXVA\_MBctrl\_I\_HostResidDiff\_1, DXVA\_MBctrl\_I\_OffHostIDCT\_1, DXVA\_MBctrl\_P\_HostResidDiff\_1, and DXVA\_MBctrl\_P\_OffHostIDCT\_1

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">wMBtype Bits</th>
<th align="left">Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>MotionType</em></p></td>
<td align="left"><p>2 (frame motion)</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>MBscanMethod</em></p></td>
<td align="left"><p>Zero (zigzag) if <strong>bConfigHostInverseScan</strong> equals zero</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>FieldResidual</em></p></td>
<td align="left"><p>Zero (frame residual)</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>H261LoopFilter</em></p></td>
<td align="left"><p>Zero (no H.261 loop filter)</p></td>
</tr>
</tbody>
</table>

 

### <span id="Restrictions_on_Bitstream_Buffers"></span><span id="restrictions_on_bitstream_buffers"></span><span id="RESTRICTIONS_ON_BITSTREAM_BUFFERS"></span>Restrictions on Bitstream Buffers

The contents of any bitstream buffer must contain data in the MPEG-1 main profile video format.

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[display\display]:%20MPEG1_A%20%20%20RELEASE:%20%282/10/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




