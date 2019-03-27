---
title: Solicitação de Certificado (Autoridade de Certificação)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Ao fazer uma solicitação de certificado para uma autoridade de certificação online (AC) (normalmente, servidores que estão em sua rede interna) na página Escolher uma Autoridade de Certificação (AC), as duas opções a seguir são apresentadas:'
ms.openlocfilehash: 64e4b5b52f0ebf6eb5dab6b60c7aa9c140ada080
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897053"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="ae9fb-103">Solicitação de Certificado (Autoridade de Certificação)</span><span class="sxs-lookup"><span data-stu-id="ae9fb-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="ae9fb-104">Ao fazer uma solicitação de certificado para uma autoridade de certificação online (AC) (normalmente, servidores que estão em sua rede interna) na página **Escolher uma Autoridade de Certificação (AC)**, as duas opções a seguir são apresentadas:</span><span class="sxs-lookup"><span data-stu-id="ae9fb-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="ae9fb-105">Selecionar uma AC na lista detectada em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="ae9fb-106">Especificar outra autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="ae9fb-107">Se você selecionar a primeira opção, você verá uma lista suspensa que contém todas as autoridades de certificação baseada no Windows Server detectados no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="ae9fb-108">Selecione a autoridade de certificação apropriada para seu certificado.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="ae9fb-109">Talvez seja necessário consultar o administrador de AC para saber qual AC escolher.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="ae9fb-p102">Se você selecionar a segunda opção, digite o nome de domínio totalmente qualificado (FQDN) e a instância de AC da autoridade de certificação que você usará para o seu certificado. Essa opção será apropriada se a AC que você deseja usar não for uma AC baseada no Windows Server, mas funcionará para ACs baseadas no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ae9fb-112">Lembre-se de confirmar as associações de grupo que precisam ser bem-sucedidas com a solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="ae9fb-113">Geralmente, as autoridades de certificação têm um requisito de permissão diferentes dos requisitos de instalação Skype para Business Server nos servidores.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="ae9fb-114">Confirme os requisitos para solicitar o certificado com seu administrador de AC.</span><span class="sxs-lookup"><span data-stu-id="ae9fb-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

