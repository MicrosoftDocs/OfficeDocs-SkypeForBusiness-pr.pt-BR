---
title: 'Sistema de Salas do Skype: licença do software Skype for Business'
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
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="1315c-103">Sistema de Salas do Skype: licença do software Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1315c-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="1315c-104">Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1315c-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="1315c-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span><span class="sxs-lookup"><span data-stu-id="1315c-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="1315c-106">Antes de implantar o primeiro , descubra o estado de licença de volume da implantação - utilizando os Servidores de Gerenciamento de Chaves (KMS) ou várias Chaves de Ativação (MAK).</span><span class="sxs-lookup"><span data-stu-id="1315c-106">Before deploying the first , find out the volume license state of the deployment – using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="1315c-107">Servidores de Gerenciamento de Chaves (KMS)</span><span class="sxs-lookup"><span data-stu-id="1315c-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="1315c-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span><span class="sxs-lookup"><span data-stu-id="1315c-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="1315c-109">Para descobrir se o KMS é válido:</span><span class="sxs-lookup"><span data-stu-id="1315c-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="1315c-110">A partir de um prompt de comando, execute: `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="1315c-110">From  a command prompt, run: `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="1315c-111">Para obter mais informações, consulte [Como descobrir os hosts de KMS do Office e do Windows via DNS e remover instâncias não autorizadashttp://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="1315c-111">For more information, see  [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instanceshttp://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="1315c-112">Para configurar um KMS, consultar [Ativação do KMS do Office 2013https://technet.microsoft.com/pt-br/library/ee624357.aspx](https://technet.microsoft.com/en-us/library/ee624357.aspx) e [GVLKs para ativação do KMS e do Active Directory do Office 2013https://technet.microsoft.com/pt-br/library/dn385360.aspx](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="1315c-112">To set up a KMS, see [KMS activation of Office 2013https://technet.microsoft.com/en-us/library/ee624357.aspx](https://technet.microsoft.com/en-us/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013https://technet.microsoft.com/en-us/library/dn385360.aspx](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="1315c-113">Chave Genérica da Licença de Volume do Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Esta chave faz com que o  procure um KMS na rede.)</span><span class="sxs-lookup"><span data-stu-id="1315c-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the  to look for a KMS on the network.)
</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="1315c-114">Vários Chaves de Ativação (MAK) do Centro de Serviços de Licença de Volume (VLSC)</span><span class="sxs-lookup"><span data-stu-id="1315c-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="1315c-115">Se o cliente utilizar qualquer outro software de licença de volume, o departamento de TI gerenciará as ativações do software e o Contrato de Licença de Volume (VLA) usando o VLSC.</span><span class="sxs-lookup"><span data-stu-id="1315c-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="1315c-116">Isto também permitirá à empresa adquirir as ativações VL do , além de obter um MAK para sua entrada no Console de Administração do .</span><span class="sxs-lookup"><span data-stu-id="1315c-116">This will also enable the company to purchase  VL activations, after which the company can obtain a MAK for input in the  Admin Console.</span></span>
  
<span data-ttu-id="1315c-117">O cliente com um VLA deve conhecer suas credenciais VLSC, que serão utilizadas para administrar o contrato e obter o MAK.</span><span class="sxs-lookup"><span data-stu-id="1315c-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="1315c-118">Em caso de dúvida, o departamento financeiro do cliente deve confirmar se o cliente pagou por um VLA.</span><span class="sxs-lookup"><span data-stu-id="1315c-118">If uncertain, the customer’s finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="1315c-119">Para obter um MAK, acesse o Centro de Serviços de Licenciamento de Volume para visualizar os contratos e fazer o download das chaves de produtos (MAK).</span><span class="sxs-lookup"><span data-stu-id="1315c-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="1315c-120">Para obter mais informações, acesse [Centro de Serviços de Licenciamento de Volumehttps://www.microsoft.com/Licensing/servicecenter/default.aspx](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="1315c-120">For more information, go to the [Volume Licensing Service Centerhttps://www.microsoft.com/Licensing/servicecenter/default.aspx](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="1315c-121">MAK para o Office 365 sem acesso VLSC</span><span class="sxs-lookup"><span data-stu-id="1315c-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="1315c-122">Se o cliente não tiver um Contrato de Licença de Volume, as ativações do serão muito mais difíceis de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="1315c-122">If the customer doesn’t have a Volume License Agreement,  activations will be much more difficult to manage.</span></span> <span data-ttu-id="1315c-123">No entanto, os clientes do Office 365 sem acesso a VLSC podem obter um MAK promocional fornecendo as informações a seguir para o OEM que estiver vendendo o :</span><span class="sxs-lookup"><span data-stu-id="1315c-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the :</span></span>
  
- <span data-ttu-id="1315c-124">Nome da empresa</span><span class="sxs-lookup"><span data-stu-id="1315c-124">Company name</span></span>
    
- <span data-ttu-id="1315c-125">Nome de contato, e-mail e número de telefone para implantação</span><span class="sxs-lookup"><span data-stu-id="1315c-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="1315c-126">Número de sistemas implantados</span><span class="sxs-lookup"><span data-stu-id="1315c-126">Number  of systems deployed</span></span>
    
- <span data-ttu-id="1315c-127">Data da implantação</span><span class="sxs-lookup"><span data-stu-id="1315c-127">Deployment date</span></span>
    
- <span data-ttu-id="1315c-128">Se o cliente tiver um Gerente de Conta Técnico da Microsoft, fornecer o nome e informações de contato do TAM</span><span class="sxs-lookup"><span data-stu-id="1315c-128">If the customer has a Microsoft Technical Account Manager, the TAM’s name and contact information</span></span>
    

