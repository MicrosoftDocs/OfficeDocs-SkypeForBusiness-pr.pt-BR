---
title: Testar as configurações do tronco SIP no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: Saiba como testar configurações de tronco SIP usando o Skype do Shell de gerenciamento do servidor de negócios.'
ms.openlocfilehash: 4e4c0c7ce117143f743dd40536bc49bfce92d978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="63b94-103">Testar as configurações do tronco SIP no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="63b94-103">Test SIP trunk configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="63b94-104">**Resumo:** Saiba como testar configurações de tronco SIP usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="63b94-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="63b94-p101">As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="63b94-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="63b94-107">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="63b94-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="63b94-108">As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="63b94-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="63b94-109">Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="63b94-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="63b94-110">Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="63b94-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="63b94-111">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="63b94-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="63b94-112">Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar se um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.</span><span class="sxs-lookup"><span data-stu-id="63b94-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="63b94-113">Definições de configuração de tronco só podem ser testadas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="63b94-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="63b94-114">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="63b94-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="63b94-115">Testar as definições da configuração do Tronco SIP</span><span class="sxs-lookup"><span data-stu-id="63b94-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="63b94-116">Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="63b94-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


