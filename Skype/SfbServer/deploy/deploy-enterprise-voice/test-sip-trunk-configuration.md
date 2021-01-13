---
title: Testar as definições de configuração do tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: Saiba como testar as definições de configuração do tronco SIP usando o Shell de Gerenciamento do Skype for Business Server.'
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830631"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b32e2-103">Testar as definições de configuração do tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b32e2-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b32e2-104">**Resumo:** Saiba como testar as definições de configuração do tronco SIP usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b32e2-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="b32e2-105">As definições de configuração do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) da IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="b32e2-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="b32e2-106">Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="b32e2-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="b32e2-107">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="b32e2-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="b32e2-108">As condições sob as quais pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados.</span><span class="sxs-lookup"><span data-stu-id="b32e2-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="b32e2-109">Se a criptografia SRTP (Secure Realtime Transport Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="b32e2-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="b32e2-110">Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você.</span><span class="sxs-lookup"><span data-stu-id="b32e2-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b32e2-111">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="b32e2-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="b32e2-112">Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar que um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.</span><span class="sxs-lookup"><span data-stu-id="b32e2-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="b32e2-113">As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b32e2-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="b32e2-114">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b32e2-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="b32e2-115">Para testar as definições de configuração do tronco SIP</span><span class="sxs-lookup"><span data-stu-id="b32e2-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="b32e2-116">Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="b32e2-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


