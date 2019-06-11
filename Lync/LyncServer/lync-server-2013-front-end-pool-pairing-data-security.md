---
title: 'Lync Server 2013: Segurança de dados de emparelhamento do pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1a408aecedc14162271d5def1adc2bcebdfd82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Segurança de dados de emparelhamento do pool Front End no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-10-07_

O serviço de backup é um mecanismo de replicação de dados introduzido no Lync Server 2013 que transfere dados de usuários e conteúdo de conferência entre dois pools front-ends em dois data centers para fins de recuperação de desastres. Os dados do usuário contêm URIs SIP do usuário, bem como as listas de contatos e as configurações. O conteúdo da conferência inclui carregamentos do Microsoft PowerPoint 2010, bem como quadros de comunicações usados em conferências. Do pool de origem, os dados do usuário e o conteúdo da conferência são exportados do armazenamento local, zipados, transferidos para o pool de destino, onde eles são descompactados e importados para armazenamento local. O Serviço de Backup pressupõe que o link de comunicações entre os dois data centers está dentro da rede corporativa que está protegida a partir da Internet. Ele não criptografa os dados transferidos entre os dois data centers, nem é encapsulado nativamente em um protocolo seguro, como HTTPS. Portanto, é possível que o ataque pelo meio Man do pessoal interno na rede da empresa seja possível.

<div>

## <a name="evaluating-security-risks"></a>Avaliando riscos de segurança

Qualquer empresa que implante o Lync Server 2013 em vários data centers e use o recurso de recuperação de desastres deve garantir que o tráfego entre o Data Center seja protegido pela intranet corporativa. As empresas que se preocupam com a proteção interna contra ataques devem proteger os links de comunicação entre os data centers.

A pressuposição de que os dados centrais de uma empresa são protegidos por trás da intranet corporativa é padrão. Há muitos outros tipos de dados confidenciais corporativos transferidos entre esses data centers. A infraestrutura de ti da empresa está a perigo risco se esses links de Data Center não estiverem protegidos.

Embora exista o risco de ataques de "intrusos" na rede corporativa, ele é relativamente limitado em comparação a expor o tráfego à Internet. Especificamente, os dados do usuário expostos pelo serviço de backup (como URIs SIP) estão disponíveis geralmente para todos os funcionários da empresa por meio de outros meios como o catálogo de endereços global pelo Exchange ou outro software de diretório. Portanto, o foco deve estar na proteção da WAN entre os dois data centers quando o serviço de backup é usado para copiar dados entre os dois pools emparelhados.

</div>

<div>

## <a name="mitigating-security-risks"></a>Redução de riscos de segurança

Há muitas maneiras de melhorar a proteção de segurança para o tráfego do serviço de backup, desde a restrição do acesso a centros de dados até a proteção do transporte de WAN entre os dois data centers. Na maioria dos casos, as empresas que implantam o Lync Server 2013 podem já ter a infraestrutura de segurança necessária implementada. Para as empresas que buscam orientação, a Microsoft oferece uma solução como um exemplo de como criar uma infraestrutura de ti segura. No entanto, isso não significa que essa é a única solução, nem significa que ela é a solução preferida para o Lync Server. Recomendamos que os clientes corporativos escolham a solução adequada às suas necessidades específicas, com base em sua infraestrutura de segurança de ti e seus requisitos. O exemplo de solução da Microsoft emprega IPSec e a política de grupo para o isolamento de servidor e domínio. Para obter detalhes, [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)consulte. Para perguntas e comentários, entre em contato com a secwish@microsoft.com.

Outra solução possível é usar o IPSec apenas para ajudar a proteger os dados enviados pelo próprio Serviço de Backup. Se você escolher este método, deverá configurar as regras do IPSec para o protocolo SMB nos seguintes servidores, onde Pool A e Pool B são dois Pools de Front-Ends emparelhados.

  - O Serviço SMB (TCP/445) de cada Servidor Front-End no Pool A para o Repositório de Arquivos usado pelo Pool B.

  - O Serviço SMB (TCP/445) de cada Servidor Front-End no Pool B para o Repositório de Arquivos usado pelo Pool A.

<div>


> [!WARNING]  
> O IPsec não deve ser usado para substituir a segurança no nível de aplicativo, como SSL/TLS. Uma vantagem de usar o IPsec é que ele pode fornecer segurança ao tráfego da rede para os aplicativos existentes sem ter de alterá-los. As empresas que desejam proteger o transporte entre os dois data centers devem consultar seus respectivos fornecedores de hardware de rede em relação à maneira de configurar conexões WAN seguras usando o equipamento do fornecedor.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

