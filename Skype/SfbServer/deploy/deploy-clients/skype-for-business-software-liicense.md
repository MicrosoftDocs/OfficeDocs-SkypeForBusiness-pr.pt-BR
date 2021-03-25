---
title: Licença de software do Skype Room System Skype for Business
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113087"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="902f1-103">Sistema de Sala do Skype: Licença de software do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="902f1-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="902f1-104">Leia este tópico para saber como verificar se você tem uma licença de volume de software do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="902f1-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="902f1-105">O Sistema de Sala do Skype usa um cliente do Skype for Business instalado, que requer uma licença de volume de software.</span><span class="sxs-lookup"><span data-stu-id="902f1-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="902f1-106">Antes de implantar o primeiro Sistema de Sala do Skype, descubra o estado de licença de volume da implantação - usando KMS (Key Management Servers) ou Multiple Activation Keys (MAK).</span><span class="sxs-lookup"><span data-stu-id="902f1-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="902f1-107">Servidores de Gerenciamento de Chaves (KMS)</span><span class="sxs-lookup"><span data-stu-id="902f1-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="902f1-108">Se o KMS estiver no local e distribuir as ativações da Licença de Volume do Skype for Business, o Sistema de Sala do Skype ativará automaticamente o cliente skype for Business.</span><span class="sxs-lookup"><span data-stu-id="902f1-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="902f1-109">Para descobrir se KMS está no local:</span><span class="sxs-lookup"><span data-stu-id="902f1-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="902f1-110">Em um prompt de comando, execute:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="902f1-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="902f1-111">Para obter mais informações, [consulte How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="902f1-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="902f1-112">Para configurar um KMS, consulte [ativação KMS do Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) e [GVLKs para KMS e](/DeployOffice/vlactivation/gvlks) ativação do Active Directory do Office 2013</span><span class="sxs-lookup"><span data-stu-id="902f1-112">To set up a KMS, see [KMS activation of Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) and [GVLKs for KMS and Active Directory activation of Office 2013](/DeployOffice/vlactivation/gvlks)</span></span>
  
<span data-ttu-id="902f1-113">Chave de Licença de Volume Genérico do Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Essa chave faz com que o Sistema de Sala do Skype procure por um KMS na rede.)</span><span class="sxs-lookup"><span data-stu-id="902f1-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="902f1-114">Mak (Várias Teclas de Ativação) do Centro de Serviço de Licença de Volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="902f1-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="902f1-115">Se o cliente usar qualquer outro software de licença de volume, o departamento de IT gerenciará as ativações de software e o Contrato de Licença de Volume (VLA) usando o VLSC.</span><span class="sxs-lookup"><span data-stu-id="902f1-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="902f1-116">Isso também permitirá que a empresa compre ativações do Skype for Business VL, após as quais a empresa poderá obter um MAK para entrada no Console de Administração do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="902f1-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="902f1-117">Um cliente com uma VLA deve conhecer suas credenciais VLSC, que serão usadas para administrar o contrato e obter MAK.</span><span class="sxs-lookup"><span data-stu-id="902f1-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="902f1-118">Se não tiver certeza, o departamento financeiro do cliente poderá confirmar se o cliente pagou por uma VLA.</span><span class="sxs-lookup"><span data-stu-id="902f1-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="902f1-119">Para obter um MAK, acesse o Centro de Serviço de Licenciamento por Volume para exibir contratos e baixar chaves de produto (MAK).</span><span class="sxs-lookup"><span data-stu-id="902f1-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="902f1-120">Para obter mais informações, acesse o Centro de [Serviços de Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="902f1-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="902f1-121">MAK para Microsoft 365 ou Office 365 sem acesso VLSC</span><span class="sxs-lookup"><span data-stu-id="902f1-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="902f1-122">Se o cliente não tiver um Contrato de Licença de Volume, as ativações do Skype for Business serão muito mais difíceis de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="902f1-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="902f1-123">No entanto, os clientes do Microsoft 365 e do Office 365 sem acesso VLSC podem obter uma MAK promocional fornecendo as seguintes informações ao OEM que vende o Sistema de Sala do Skype:</span><span class="sxs-lookup"><span data-stu-id="902f1-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="902f1-124">Nome da empresa</span><span class="sxs-lookup"><span data-stu-id="902f1-124">Company name</span></span>
    
- <span data-ttu-id="902f1-125">Nome de contato de implantação, email e número de telefone</span><span class="sxs-lookup"><span data-stu-id="902f1-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="902f1-126">Número de sistemas implantados</span><span class="sxs-lookup"><span data-stu-id="902f1-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="902f1-127">Data de implantação</span><span class="sxs-lookup"><span data-stu-id="902f1-127">Deployment date</span></span>
    
- <span data-ttu-id="902f1-128">Se o cliente tiver um Gerenciador de Contas Técnicas da Microsoft, o nome e as informações de contato do TAM</span><span class="sxs-lookup"><span data-stu-id="902f1-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
