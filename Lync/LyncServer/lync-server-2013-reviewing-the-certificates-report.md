---
title: 'Lync Server 2013: examinando o relatório de certificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a01f778e855fc5934b524c5bf4a5829a2ca31e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="775d8-102">Examinando o relatório de certificados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="775d8-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="775d8-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="775d8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="775d8-104">O relatório de certificados contém todos os certificados necessários na implantação do Lync Server 2013 recomendada.</span><span class="sxs-lookup"><span data-stu-id="775d8-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="775d8-105">A ferramenta de planejamento conta os nomes de entidades e os nomes alternativos da entidade que são inseridos.</span><span class="sxs-lookup"><span data-stu-id="775d8-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="775d8-106">O texto padrão que é deixado não editado pode representar um possível desafio para a equipe responsável por solicitar e emitir os certificados.</span><span class="sxs-lookup"><span data-stu-id="775d8-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="775d8-107">As informações do certificado também incluem informações sobre o local de onde o certificado pode ser normalmente emitido.</span><span class="sxs-lookup"><span data-stu-id="775d8-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="775d8-108">Se a infraestrutura não tiver uma infraestrutura de chave pública interna (PKI), todos os certificados poderão ser solicitados por meio de um provedor de certificados público.</span><span class="sxs-lookup"><span data-stu-id="775d8-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="775d8-109">Os campos EKU (Uso Estendido de Chave) e Atribuir a do relatório são muito úteis para ajudar a compreender quais devem ser a finalidade e a localização de cada certificado.</span><span class="sxs-lookup"><span data-stu-id="775d8-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="775d8-110">![Relatório de administração de certificados](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Relatório de administração de certificados")</span><span class="sxs-lookup"><span data-stu-id="775d8-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="775d8-111">Revise cuidadosamente e certifique-se de entender, o uso e a finalidade de cada certificado na implantação.</span><span class="sxs-lookup"><span data-stu-id="775d8-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="775d8-112">Se houver uma pergunta sobre o que um certificado faz, determine qual servidor ou serviço está falando com o que.</span><span class="sxs-lookup"><span data-stu-id="775d8-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="775d8-113">Os certificados no Lync Server 2013 são usados para duas finalidades principais:</span><span class="sxs-lookup"><span data-stu-id="775d8-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="775d8-114">Protocolo MTLS (Mutual Transport Layer Security) – os computadores envolvidos na comunicação cada apresentam um certificado que comprova sua identidade para outro computador.</span><span class="sxs-lookup"><span data-stu-id="775d8-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="775d8-115">Isso é conhecido como autenticação de servidor.</span><span class="sxs-lookup"><span data-stu-id="775d8-115">This is known as server authentication.</span></span> <span data-ttu-id="775d8-116">A comunicação não pode começar até que cada computador confie na identidade do outro computador.</span><span class="sxs-lookup"><span data-stu-id="775d8-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="775d8-117">Criptografia: a criptografia (Secure Sockets Layer, ou SSL, e Transport Layer Security, ou TLS) é um meio fundamental para ajudar a proteger as comunicações, ajudar a garantir a privacidade e criar um sistema confiável de colaboração e comunicação.</span><span class="sxs-lookup"><span data-stu-id="775d8-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="775d8-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="775d8-118">See Also</span></span>


[<span data-ttu-id="775d8-119">Revisando os relatórios do administrador no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="775d8-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

