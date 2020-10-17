---
title: 'Lync Server 2013: coleta de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01e6c75a4a557ff44d626f006210bec3a3c38472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516568"
---
# <a name="data-collection-in-lync-server-2013"></a>Coleta de dados no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

No software de comunicações do Microsoft Lync Server 2013, você pode executar a ferramenta de planejamento do Microsoft Lync Server 2013, sem documentar os endereços IP e os nomes de domínio totalmente qualificados do servidor de borda (FQDNs) existentes, mas é significativamente mais difícil de fazê-lo sem causar erros de configuração. Por exemplo, se a coexistência for necessária por um período de tempo, um erro comum é reutilizar FQDNs de uma implantação de borda existente para sua implantação de borda do Lync Server 2013. Com os endereços IP e os FQDNs existentes e propostos escritos em uma planilha, tabela ou outro formulário Visual, você ajuda a evitar problemas de instalação durante a instalação.

<div>


> [!WARNING]  
> Se você usou versões anteriores da ferramenta de planejamento, talvez tenha usado a ferramenta para criar sua topologia e o documento de topologia exportado para uso no construtor de topologias para publicar sua topologia. A capacidade de exportar a topologia foi removida da ferramenta de planejamento. O uso de uma versão anterior da ferramenta de planejamento para criar um documento de topologia para o Lync Server 2013 é fortemente desencorajado e produzirá resultados inesperados.



</div>

Portanto, a abordagem recomendada é usar o modelo de conjunto de dados a seguir, que corresponde à sua topologia de borda, para coletar os vários endereços IP e FQDN que você precisará inserir na ferramenta de planejamento. Ao documentar a configuração atual e proposta, você pode colocar os valores no contexto apropriado para seu ambiente de produção. E, você é obrigado a pensar sobre como você irá configurar a coexistência e recursos como URLs simples, compartilhamento de arquivos e balanceamento de carga.

Para implantar o Microsoft Lync Server 2013 com êxito, você precisa entender a interação e a confiança dos componentes individuais. Ao coletar dados de sua infraestrutura de rede e de servidor existente e aplicar as diretrizes de planejamento nessas seções, você pode integrar os componentes do servidor de borda do Lync Server 2013 à sua infraestrutura.

Apresentado na [escolha de uma topologia no Lync Server 2013](lync-server-2013-choosing-a-topology.md), há três arquiteturas principais com duas variações, para um total de cinco cenários de implantação possíveis. Um desses cenários será o ponto de partida para sua coleção de dados. Os endereços IP, os nomes de servidor e os nomes de domínio são exemplos que coincidem com o certificado correspondente, o firewall e os diagramas DNS que detalham as informações necessárias para uma solução de planejamento completa. Os diagramas e o preenchimento de seus valores obrigatórios de certificado, DNS e firewall são especialmente importantes em comunicações entre equipes, onde o gerenciamento da autoridade de certificação, a configuração de firewall e o DNS é gerenciado por equipes diferentes da equipe que planeja a implantação. Os diagramas fornecem informações sobre os componentes necessários que podem ser usados para comunicar esses requisitos para colaboração entre equipes.

Os diagramas fornecidos são intencionalmente genéricos, mas permitem que a coleção de todos os dados pertinentes seja necessária para a comunicação de requisitos em um cenário de equipe cruzado em que a rede, o firewall, a criação e o gerenciamento de certificados, a implantação de servidor e o gerenciamento de servidores são tratados por grupos diferentes. Ter os detalhes necessários para a configuração de rede, firewalls, portas e protocolos, certificados e servidores é inestimável quando a implantação do Lync Server está em andamento.

**Servidor de borda e pool de borda**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Proxy reverso**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Diretor ou pool de diretor**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

