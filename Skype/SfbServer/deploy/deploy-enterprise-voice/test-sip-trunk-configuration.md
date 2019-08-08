---
title: Testar as configurações de tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: saiba como testar as configurações de configuração de tronco SIP usando o Shell de gerenciamento do Skype for Business Server.'
ms.openlocfilehash: 1ef034f0b1de187e472fc3049573e9453e5a9505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240105"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e65a8-103">Testar as configurações de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e65a8-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e65a8-104">**Resumo:** Saiba como testar as definições de configuração de tronco SIP usando o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e65a8-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="e65a8-p101">As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="e65a8-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="e65a8-107">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="e65a8-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="e65a8-108">As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="e65a8-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="e65a8-109">Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="e65a8-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="e65a8-110">Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="e65a8-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e65a8-111">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="e65a8-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="e65a8-112">Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar se um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.</span><span class="sxs-lookup"><span data-stu-id="e65a8-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="e65a8-113">As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet  [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e65a8-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="e65a8-114">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e65a8-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="e65a8-115">Testar as definições da configuração do Tronco SIP</span><span class="sxs-lookup"><span data-stu-id="e65a8-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="e65a8-116">Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="e65a8-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


