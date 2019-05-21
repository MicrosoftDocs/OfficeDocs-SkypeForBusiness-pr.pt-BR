---
title: Testar as configurações de tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. '
ms.openlocfilehash: 9f254d833f5d679343a39062bc2ed68c9122af56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274916"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="387b2-103">Testar as configurações de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="387b2-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="387b2-104">As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="387b2-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="387b2-105">Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="387b2-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="387b2-106">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="387b2-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="387b2-107">As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="387b2-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="387b2-108">Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="387b2-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="387b2-109">Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="387b2-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="387b2-110">Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="387b2-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="387b2-111">Os administradores também podem usar o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) para verificar se um tronco pode converter um número como discado por um usuário para um número que possa ser administrado pelo Gateway.</span><span class="sxs-lookup"><span data-stu-id="387b2-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="387b2-112">As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet  Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="387b2-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="387b2-113">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="387b2-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="387b2-114">**Testar as definições da configuração do Tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="387b2-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="387b2-115">Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="387b2-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
