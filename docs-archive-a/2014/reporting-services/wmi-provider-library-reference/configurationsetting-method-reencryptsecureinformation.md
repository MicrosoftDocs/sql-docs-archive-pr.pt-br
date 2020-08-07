---
title: Método ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ReencryptSecureInformation method
ms.assetid: 8a487497-c207-45b2-8c92-87c58cc68716
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1a0c657b69d624df8895ae4d5a6d12277b011b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576204"
---
# <a name="reencryptsecureinformation-method-wmi-msreportserver_configurationsetting"></a>Método ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting)
  Gera uma nova chave de criptografia e criptografa novamente todas as informações seguras no catálogo usando essa nova chave.  
  
## <a name="syntax"></a>Sintaxe  
  
```vb  
Public Sub ReencryptSecureInformation(ByRef HRESULT as Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ReencryptSecureInformation (out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a>parâmetros  
 *HRESULT*  
 [out] Valor que indica se a chamada obteve êxito ou falhou.  
  
 *ExtendedErrors[]*  
 [fora] Uma matriz de cadeia de caracteres que contém erros adicionais retornados pela chamada.  
  
## <a name="return-value"></a>Valor retornado  
 Retorna um *HRESULT* indicando êxito ou falha da chamada do método. Um valor 0 indica que a chamada do método teve êxito. Um valor diferente de zero indica que ocorreu um erro.  
  
## <a name="remarks"></a>Comentários  
 O método ReencryptSecureInformation permite que o administrador substitua a chave de criptografia existente com uma chave nova.  
  
 Quando esse método é chamado, o servidor de relatório gera uma nova chave de criptografia e itera por meio de todo o conteúdo criptografado para criptografá-lo novamente com a nova chave de criptografia.  
  
 As extensões de entrega podem armazenar informações seguras em suas estruturas de configurações de entrega. Quando o ReencryptSecureInformation é chamado, o servidor de relatório carrega cada assinatura e a extensão de entrega correspondente para criptografar novamente as informações armazenadas nas configurações associadas.  
  
 Se esse método for executado em um computador em uma implantação de expansão, cada computador na implantação de expansão precisará ser inicializado novamente.  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Consulte Também  
 [Membros de MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
