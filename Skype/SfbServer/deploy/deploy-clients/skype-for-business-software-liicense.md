---
title: Skype sala sistema Skype para a licença do software de negócios
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business.
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="24c9f-103">Sistema de Salas do Skype: licença do software Skype for Business</span><span class="sxs-lookup"><span data-stu-id="24c9f-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="24c9f-104">Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="24c9f-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="24c9f-105">Sistema de sala do Skype usa um Skype instalado para cliente corporativos, que requer uma licença de volume do software.</span><span class="sxs-lookup"><span data-stu-id="24c9f-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="24c9f-106">Antes de implantar o sistema de sala Skype primeiro, descubra o estado da licença de volume da implantação - usando servidores de gerenciamento de chaves (KMS) ou chaves de ativação múltipla (MAK).</span><span class="sxs-lookup"><span data-stu-id="24c9f-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="24c9f-107">Servidores de Gerenciamento de Chaves (KMS)</span><span class="sxs-lookup"><span data-stu-id="24c9f-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="24c9f-108">Se KMS estão funcionando e distribuirá Skype para ativações de licença de Volume de negócios, o sistema de sala Skype ativa automaticamente o Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="24c9f-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="24c9f-109">Para descobrir se o KMS é válido:</span><span class="sxs-lookup"><span data-stu-id="24c9f-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="24c9f-110">No prompt de comando, execute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="24c9f-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="24c9f-111">Para obter mais informações, consulte [como descobrir o Office e o KMS do Windows hosts por meio de DNS e remova as instâncias não autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="24c9f-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="24c9f-112">Para configurar um KMS, consulte [ativação do KMS do Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) e [GVLKs para ativação KMS and Active Directory do Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="24c9f-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="24c9f-113">Chave de licença de Volume do Office 2013 genérico para o Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (essa chave faz com que o sistema de sala Skype procurar um KMS na rede.)</span><span class="sxs-lookup"><span data-stu-id="24c9f-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="24c9f-114">Vários Chaves de Ativação (MAK) do Centro de Serviços de Licença de Volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="24c9f-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="24c9f-115">Se o cliente utilizar qualquer outro software de licença de volume, o departamento de TI gerenciará as ativações do software e o Contrato de Licença de Volume (VLA) usando o VLSC.</span><span class="sxs-lookup"><span data-stu-id="24c9f-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="24c9f-116">Isso também permitirá a empresa adquirir Skype para ativações VL de negócios, após o qual a empresa pode obter uma chave MAK para entrada no Console de administração do sistema Skype sala.</span><span class="sxs-lookup"><span data-stu-id="24c9f-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="24c9f-117">O cliente com um VLA deve conhecer suas credenciais VLSC, que serão utilizadas para administrar o contrato e obter o MAK.</span><span class="sxs-lookup"><span data-stu-id="24c9f-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="24c9f-118">Se estiver em dúvida, departamento de finanças do cliente deve ser capaz de confirmar se o cliente pagou para um VLA.</span><span class="sxs-lookup"><span data-stu-id="24c9f-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="24c9f-119">Para obter um MAK, acesse o Centro de Serviços de Licenciamento de Volume para visualizar os contratos e fazer o download das chaves de produtos (MAK).</span><span class="sxs-lookup"><span data-stu-id="24c9f-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="24c9f-120">Para obter mais informações, vá para o [Centro de atendimento de licenciamento por Volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="24c9f-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="24c9f-121">MAK para o Office 365 sem acesso VLSC</span><span class="sxs-lookup"><span data-stu-id="24c9f-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="24c9f-122">Se o cliente não tiver um contrato de licença de Volume, Skype para ativações de negócios será muito mais difícil de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="24c9f-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="24c9f-123">No entanto, os clientes do Office 365 sem acesso ao VLSC podem obter uma MAK promocional, fornecendo as seguintes informações ao OEM vendendo o sistema de sala Skype:</span><span class="sxs-lookup"><span data-stu-id="24c9f-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="24c9f-124">Nome da empresa</span><span class="sxs-lookup"><span data-stu-id="24c9f-124">Company name</span></span>
    
- <span data-ttu-id="24c9f-125">Nome de contato, e-mail e número de telefone para implantação</span><span class="sxs-lookup"><span data-stu-id="24c9f-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="24c9f-126">Número de sistemas implantados</span><span class="sxs-lookup"><span data-stu-id="24c9f-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="24c9f-127">Data da implantação</span><span class="sxs-lookup"><span data-stu-id="24c9f-127">Deployment date</span></span>
    
- <span data-ttu-id="24c9f-128">Se o cliente tiver um Microsoft gerente técnico da conta, nome e informações de contato do TAM</span><span class="sxs-lookup"><span data-stu-id="24c9f-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

