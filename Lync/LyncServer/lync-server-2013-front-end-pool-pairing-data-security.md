---
title: 'Lync Server 2013: segurança de dados de emparelhamento do pool de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 503a5a02d4412fe2bbbf5f1882e3d7d117640576
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Segurança de dados de emparelhamento do pool de front-ends no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-10-07_

O serviço de backup é um mecanismo de replicação de dados introduzido no Lync Server 2013 que transfere o conteúdo de conferência e dados de usuários entre dois pools de front-ends emparelhados em dois data centers para fins de recuperação de desastres. Os dados dos usuários contêm as SIP URIs dos usuários, bem como listas de contatos e configurações. O conteúdo de conferência inclui carregamentos do Microsoft PowerPoint 2010, bem como quadros de comunicações usados em conferências. Do pool de origem, os dados dos usuários e o conteúdo das conferências são exportados do armazenamento local, compactados, transferidos para o Pool de destino, onde são descompactados e importados ao armazenamento local. O Serviço de Backup pressupõe que o link de comunicação entre os dois data centers está dentro da rede da empresa, protegida da Internet. Ele não criptografa os dados transferidos entre os dois data centers, nem está encapsulado de forma nativa em um protocolo protegido, como HTTPS. Portanto, o ataque de "intrusos" de pessoal interno na rede da empresa é possível.

<div>

## <a name="evaluating-security-risks"></a>Avaliação dos riscos à segurança

Qualquer empresa que implanta o Lync Server 2013 em vários data centers e usa o recurso de recuperação de desastres deve garantir que o tráfego entre data centers seja protegido pela intranet corporativa. As empresas que se preocupam com proteção interna contra ataques devem proteger os links de comunicação entre os data centers.

A presunção de que os data centers de uma empresa estão protegidos atrás da Intranet da empresa é padrão. Há muitos outros tipos de dados empresariais sensíveis transferidos entre esses data centers. A infraestrutura de TI da empresa corre grande perigo se esses links entre os data centers não forem protegidos.

Embora exista o risco de ataques de "intrusos" na rede da empresa, ele é relativamente limitado em comparação a expor o tráfego à Internet. Especificamente, os dados dos usuários expostos pelo Serviço de Backup (como SIP URIs) estão geralmente disponíveis para todos os funcionários da empresa através de outros meios como o Catálogo de Endereços Global do Exchange ou outro software de diretório. Portanto, o foco deve estar em proteger a WAN entre os dois data centers quando o Serviço de Backup é usado para copiar dados entre dois Pools emparelhados.

</div>

<div>

## <a name="mitigating-security-risks"></a>Mitigação dos riscos à segurança

Há várias maneiras de aprimorar a proteção de segurança para o tráfego do serviço de backup, variando de restringir o acesso aos data centers para proteger o transporte de WAN entre os dois data centers. Na maioria dos casos, as empresas que estão implantando o Lync Server 2013 talvez já tenham a infraestrutura de segurança necessária em vigor. Para empresas que procuram orientações, a Microsoft oferece uma solução como um exemplo de como criar uma infraestrutura de ti segura. No entanto, isso não significa que é a única solução, nem significa que ela é a solução preferida para o Lync Server. Recomendamos que os clientes corporativos escolham a solução adequada às suas necessidades específicas, com base em sua infraestrutura de segurança de ti e seus requisitos. O exemplo de solução da Microsoft emprega IPSec e diretiva de grupo para o isolamento de servidor e domínio. Para obter detalhes, [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544)consulte. Para perguntas e comentários, entre em contato com secwish@microsoft.com.

Outra solução possível é usar o IPSec apenas para ajudar a proteger os dados enviados pelo próprio serviço de backup. Se você escolher esse método, deverá configurar as regras IPSec para o protocolo SMB para os servidores a seguir, em que o pool A e o pool B são dois pools de front-ends emparelhados.

  - O serviço SMB (TCP/445) de cada servidor front-end no pool A para o repositório de arquivos usado pelo pool B.

  - O serviço SMB (TCP/445) de cada servidor front-end no pool B para o repositório de arquivos usado pelo pool A.

<div>


> [!WARNING]  
> O IPsec não se destina a substituir a segurança no nível do aplicativo, como SSL/TLS. Uma vantagem de usar o IPsec é que ele pode fornecer segurança de tráfego de rede para aplicativos existentes sem precisar alterá-los. As empresas que desejam apenas proteger o transporte entre os dois data centers devem consultar seus respectivos fornecedores de hardware de rede sobre maneiras de configurar conexões WAN seguras usando o equipamento do fornecedor.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

