---
title: Solicitação de Certificado (Autoridade de Certificação)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Ao fazer uma solicitação de certificado para uma autoridade de certificação online (CA) (normalmente, são servidores que estão em sua rede interna) na página Escolher uma Autoridade de Certificação (CA), as duas opções a seguir são apresentadas:'
ms.openlocfilehash: 0081ab852a1650dfafd61471891a002be60def3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805321"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="c7221-103">Solicitação de Certificado (Autoridade de Certificação)</span><span class="sxs-lookup"><span data-stu-id="c7221-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="c7221-104">Ao fazer uma solicitação de certificado para uma autoridade de certificação online (CA) (normalmente, são servidores que estão em sua rede interna) na página **Escolher uma Autoridade de Certificação (CA)**, as duas opções a seguir são apresentadas:</span><span class="sxs-lookup"><span data-stu-id="c7221-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="c7221-105">Selecionar um CA na lista detectada em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c7221-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="c7221-106">Especificar outra autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="c7221-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="c7221-107">Se você selecionar a primeira opção, verá uma listada que contém todas as autoridades de certificação baseadas no Windows Server detectadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c7221-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="c7221-108">Selecione a autoridade de certificação apropriada para seu certificado.</span><span class="sxs-lookup"><span data-stu-id="c7221-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="c7221-109">Talvez seja necessário consultar seu administrador de CA para saber qual CA escolher.</span><span class="sxs-lookup"><span data-stu-id="c7221-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="c7221-p102">Se você selecionar a segunda opção, digite o nome de domínio totalmente qualificado (FQDN) e a instância de CA para a autoridade de certificação que você usará para seu certificado. Essa opção será apropriada se a CA que você deseja usar não for uma CA com base no Windows Server, mas funcionará para CAs baseadas no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c7221-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c7221-112">Lembre-se de confirmar as associações de grupo que precisam ser bem-sucedidas com a solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="c7221-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="c7221-113">Normalmente, as autoridades de certificação têm um requisito de permissão diferente dos requisitos para instalar o Skype for Business Server nos servidores.</span><span class="sxs-lookup"><span data-stu-id="c7221-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="c7221-114">Confirme os requisitos para solicitar o certificado com seu administrador de CA
.</span><span class="sxs-lookup"><span data-stu-id="c7221-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

