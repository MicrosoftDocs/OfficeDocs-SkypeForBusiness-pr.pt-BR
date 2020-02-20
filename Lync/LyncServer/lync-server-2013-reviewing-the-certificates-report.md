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
ms.openlocfilehash: a584f331deaf702305367042c6c40679ffb7099f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Examinando o relatório de certificados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

O relatório de certificados contém todos os certificados necessários na implantação do Lync Server 2013 recomendada. A ferramenta de planejamento conta os nomes de entidades e os nomes alternativos da entidade que são inseridos. O texto padrão que é deixado não editado pode representar um possível desafio para a equipe responsável por solicitar e emitir os certificados. As informações do certificado também incluem informações sobre o local de onde o certificado pode ser normalmente emitido. Se a infraestrutura não tiver uma infraestrutura de chave pública interna (PKI), todos os certificados poderão ser solicitados por meio de um provedor de certificados público. Os campos EKU (Uso Estendido de Chave) e Atribuir a do relatório são muito úteis para ajudar a compreender quais devem ser a finalidade e a localização de cada certificado.

![Relatório de administração de certificados](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Relatório de administração de certificados")

Revise cuidadosamente e certifique-se de entender, o uso e a finalidade de cada certificado na implantação. Se houver uma pergunta sobre o que um certificado faz, determine qual servidor ou serviço está falando com o que. Os certificados no Lync Server 2013 são usados para duas finalidades principais:

  - Protocolo MTLS (Mutual Transport Layer Security) – os computadores envolvidos na comunicação cada apresentam um certificado que comprova sua identidade para outro computador. Isso é conhecido como autenticação de servidor. A comunicação não pode começar até que cada computador confie na identidade do outro computador.

  - Criptografia: a criptografia (Secure Sockets Layer, ou SSL, e Transport Layer Security, ou TLS) é um meio fundamental para ajudar a proteger as comunicações, ajudar a garantir a privacidade e criar um sistema confiável de colaboração e comunicação.

<div>

## <a name="see-also"></a>Confira também


[Revisando os relatórios do administrador no Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

