---
title: Licença de software do Skype for Business do sistema de salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leia este tópico para saber como verificar se você tem uma licença de volume de software do Skype for Business.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220921"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="b696c-103">Sistema de salas do Skype: licença de software do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b696c-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="b696c-104">Leia este tópico para saber como verificar se você tem uma licença de volume de software do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b696c-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="b696c-105">O sistema de salas do Skype usa um cliente do Skype for Business instalado, que requer uma licença de volume do software.</span><span class="sxs-lookup"><span data-stu-id="b696c-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="b696c-106">Antes de implantar o primeiro sistema de sala do Skype, descubra o estado de licença de volume da implantação – usando os servidores de gerenciamento de chaves (KMS) ou várias chaves de ativação (MAK).</span><span class="sxs-lookup"><span data-stu-id="b696c-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="b696c-107">Servidores de gerenciamento de chaves (KMS)</span><span class="sxs-lookup"><span data-stu-id="b696c-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="b696c-108">Se o KMS estiver em vigor e distribuirá as ativações de licença de volume do Skype for Business, o sistema de salas do Skype ativará automaticamente o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b696c-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="b696c-109">Para descobrir se o KMS está no local:</span><span class="sxs-lookup"><span data-stu-id="b696c-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="b696c-110">A partir de um prompt de comando, execute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="b696c-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="b696c-111">Para obter mais informações, consulte [como descobrir hosts KMS do Office e do Windows via DNS e remover instâncias não autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="b696c-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="b696c-112">Para configurar um KMS, confira [ativação do kms do office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLKs para ativação do KMS e do Active Directory do Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="b696c-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="b696c-113">Chave genérica de licença de volume do Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta chave faz com que o sistema de salas do Skype procure um KMS na rede.)</span><span class="sxs-lookup"><span data-stu-id="b696c-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="b696c-114">Chaves de ativação múltipla (MAK) do centro de serviços de licenciamento por volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="b696c-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="b696c-115">Se o cliente usar qualquer outro software de licença de volume, o departamento de ti gerenciará as ativações de software e o contrato de licença de volume (VLA) usando o VLSC.</span><span class="sxs-lookup"><span data-stu-id="b696c-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="b696c-116">Isso também permitirá que a empresa adquira as ativações VL do Skype for Business, após a qual a empresa pode obter uma MAK para entrada no console de administração do sistema de salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="b696c-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="b696c-117">Um cliente com um VLA deve conhecer suas credenciais do VLSC, que serão usadas para administrar o contrato e obter a MAK.</span><span class="sxs-lookup"><span data-stu-id="b696c-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="b696c-118">Se certeza, o departamento financeiro do cliente deve ser capaz de confirmar se o cliente pagou por um VLA.</span><span class="sxs-lookup"><span data-stu-id="b696c-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="b696c-119">Para obter uma MAK, acesse o centro de serviços de licenciamento por volume para exibir contratos e baixar chaves do produto (MAK).</span><span class="sxs-lookup"><span data-stu-id="b696c-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="b696c-120">Para obter mais informações, vá para o [centro de serviços de licenciamento por volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="b696c-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="b696c-121">MAK para o Microsoft 365 ou o Office 365 sem acesso VLSC</span><span class="sxs-lookup"><span data-stu-id="b696c-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="b696c-122">Se o cliente não tiver um contrato de licença por volume, as ativações do Skype for Business serão muito mais difíceis de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="b696c-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="b696c-123">No entanto, os clientes do Microsoft 365 e do Office 365 sem o VLSC Access podem obter uma MAK promocional fornecendo as seguintes informações ao OEM vendendo o sistema de salas do Skype:</span><span class="sxs-lookup"><span data-stu-id="b696c-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="b696c-124">Nome da empresa</span><span class="sxs-lookup"><span data-stu-id="b696c-124">Company name</span></span>
    
- <span data-ttu-id="b696c-125">Nome do contato, email e número de telefone da implantação</span><span class="sxs-lookup"><span data-stu-id="b696c-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="b696c-126">Número de sistemas implantados</span><span class="sxs-lookup"><span data-stu-id="b696c-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="b696c-127">Data de implantação</span><span class="sxs-lookup"><span data-stu-id="b696c-127">Deployment date</span></span>
    
- <span data-ttu-id="b696c-128">Se o cliente tiver um gerente de conta técnico da Microsoft, o nome do TAM e as informações de contato</span><span class="sxs-lookup"><span data-stu-id="b696c-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

