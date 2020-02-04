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
ms.openlocfilehash: 410e9e99fccae7378b5260c9aa3a2281a3004cd5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Examinando o relatório de certificados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

O relatório de certificados contém todos os certificados necessários na implantação do Lync Server 2013 recomendado. A ferramenta de planejamento conta os nomes de assunto e os nomes alternativos de assunto que são inseridos. O texto padrão que é mantido sem edição pode representar um desafio potencial para a equipe responsável pela solicitação e emissão dos certificados. As informações do certificado também incluem informações sobre o local de onde o certificado pode ser normalmente emitido. Se a infraestrutura não tiver uma infraestrutura de chave pública interna (PKI), todos os certificados poderão ser solicitados por meio de um provedor de certificados público. Os campos EKU (Uso Estendido de Chave) e Atribuir a do relatório são muito úteis para ajudar a compreender quais devem ser a finalidade e a localização de cada certificado.

![Relatório de administradores de certificados](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Relatório de administradores de certificados")

Leia com atenção e compreenda o uso e a finalidade de cada certificado na implantação. Se houver uma dúvida sobre o que faz um certificado, determine qual servidor ou serviço está se comunicando com o que. Os certificados no Lync Server 2013 são usados para dois objetivos principais:

  - MTLS (Mutual Transport Layer Security): cada um dos computadores envolvidos na comunicação apresenta um certificado que prova sua identidade para outro computador. Isso é conhecido como autenticação de servidor. A comunicação não pode começar até que cada computador confie na identidade de outro computador.

  - Criptografia: a criptografia (Secure Sockets Layer, ou SSL, e Transport Layer Security, ou TLS) é um meio fundamental para ajudar a proteger as comunicações, ajudar a garantir a privacidade e criar um sistema confiável de colaboração e comunicação.

<div>

## <a name="see-also"></a>Confira também


[Revisando os Relatórios do Administrador no Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

