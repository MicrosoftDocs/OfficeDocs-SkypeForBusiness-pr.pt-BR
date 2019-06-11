---
title: 'Lync Server 2013: examinando o relatório de certificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="fa850-102">Examinando o relatório de certificados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa850-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa850-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fa850-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fa850-104">O relatório de certificados contém todos os certificados necessários na implantação do Lync Server 2013 recomendado.</span><span class="sxs-lookup"><span data-stu-id="fa850-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="fa850-105">A ferramenta de planejamento conta os nomes de assunto e os nomes alternativos de assunto que são inseridos.</span><span class="sxs-lookup"><span data-stu-id="fa850-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="fa850-106">O texto padrão que é mantido sem edição pode representar um desafio potencial para a equipe responsável pela solicitação e emissão dos certificados.</span><span class="sxs-lookup"><span data-stu-id="fa850-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="fa850-107">As informações do certificado também incluem informações sobre o local de onde o certificado pode ser normalmente emitido.</span><span class="sxs-lookup"><span data-stu-id="fa850-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="fa850-108">Se a infraestrutura não tiver uma infraestrutura de chave pública interna (PKI), todos os certificados poderão ser solicitados por meio de um provedor de certificados público.</span><span class="sxs-lookup"><span data-stu-id="fa850-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="fa850-109">Os campos EKU (Uso Estendido de Chave) e Atribuir a do relatório são muito úteis para ajudar a compreender quais devem ser a finalidade e a localização de cada certificado.</span><span class="sxs-lookup"><span data-stu-id="fa850-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="fa850-110">![Relatório de administradores de certificados] (images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Relatório de administradores de certificados")</span><span class="sxs-lookup"><span data-stu-id="fa850-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="fa850-111">Leia com atenção e compreenda o uso e a finalidade de cada certificado na implantação.</span><span class="sxs-lookup"><span data-stu-id="fa850-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="fa850-112">Se houver uma dúvida sobre o que faz um certificado, determine qual servidor ou serviço está se comunicando com o que.</span><span class="sxs-lookup"><span data-stu-id="fa850-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="fa850-113">Os certificados no Lync Server 2013 são usados para dois objetivos principais:</span><span class="sxs-lookup"><span data-stu-id="fa850-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="fa850-p103">MTLS (Mutual Transport Layer Security): cada um dos computadores envolvidos na comunicação apresenta um certificado que prova sua identidade para outro computador. Isso é conhecido como autenticação de servidor. A comunicação não pode começar até que cada computador confie na identidade de outro computador.</span><span class="sxs-lookup"><span data-stu-id="fa850-p103">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer. This is known as server authentication. Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="fa850-117">Criptografia: a criptografia (Secure Sockets Layer, ou SSL, e Transport Layer Security, ou TLS) é um meio fundamental para ajudar a proteger as comunicações, ajudar a garantir a privacidade e criar um sistema confiável de colaboração e comunicação.</span><span class="sxs-lookup"><span data-stu-id="fa850-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fa850-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa850-118">See Also</span></span>


[<span data-ttu-id="fa850-119">Revisando os Relatórios do Administrador no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa850-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

