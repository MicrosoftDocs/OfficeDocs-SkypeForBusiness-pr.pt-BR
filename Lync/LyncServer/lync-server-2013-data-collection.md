---
title: 'Lync Server 2013: Coleta de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Coleta de dados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

No software de comunicação do Microsoft Lync Server 2013, você pode executar o Microsoft Lync Server 2013, ferramenta de planejamento sem documentar os endereços IP existentes e propostos e os nomes de domínio totalmente qualificados do servidor de borda (FQDNs), mas é muito mais difícil de fazer Portanto, sem causar erros de configuração. Por exemplo, se a coexistência for necessária por um período de tempo, um erro comum será reutilizar FQDNs de uma implantação de borda existente para a implantação de borda do Lync Server 2013. Ao ter os endereços IP existentes e propostos e FQDNs gravados em uma planilha, tabela ou outro formulário Visual, você ajuda a evitar problemas de instalação durante a instalação.

<div>


> [!WARNING]  
> Se você usou versões anteriores da ferramenta de planejamento, talvez tenha usado a ferramenta para criar sua topologia e o documento de topologia exportado para uso no construtor de topologias para publicar sua topologia. A capacidade de exportar a topologia foi removida da ferramenta de planejamento. Usar uma versão anterior da ferramenta de planejamento para criar um documento de topologia para o Lync Server 2013 é altamente desencorajado e produzirá resultados inesperados.



</div>

Portanto, a abordagem recomendada é usar o modelo de coleta de dados a seguir, que corresponde à sua topologia de borda, para coletar os vários endereços IP e FQDN que você precisará inserir na ferramenta de planejamento. Ao documentar a configuração atual e proposta, você pode colocar os valores no contexto apropriado para o seu ambiente de produção. E você é obrigado a pensar sobre como você configurará a coexistência e recursos como URLs simples, compartilhamentos de arquivos e balanceamento de carga.

Para implantar com êxito o Microsoft Lync Server 2013, você precisa entender a interação e a confiança dos componentes individuais. Coletando dados da infraestrutura de rede e do servidor existentes e aplicando as diretrizes de planejamento nessas seções, você pode integrar componentes do Lync Server 2013 Edge Server à sua infraestrutura.

Introduzidas na [escolha de uma topologia no Lync Server 2013](lync-server-2013-choosing-a-topology.md), há três arquiteturas principais com duas variações, para um total de cinco possíveis cenários de implantação. Um desses cenários será o ponto de partida para sua coleta de dados. Os endereços IP, nomes de servidor e nomes de domínio são exemplos que coincidem com o certificado, o firewall e os diagramas DNS correspondentes que detalham as informações necessárias para uma solução de planejamento completa. Os diagramas e o preenchimento dos seus valores obrigatórios de certificado, DNS e firewall são especialmente importantes em comunicações entre equipes onde o gerenciamento da autoridade de certificação, a configuração de firewall e o DNS são gerenciados por equipes diferentes da equipe que planeja a implantação. Os diagramas fornecem informações sobre os componentes obrigatórios que podem ser usados para comunicar esses requisitos de colaboração entre a equipe.

Os diagramas fornecidos são intencionalmente genéricos, mas permitem a coleta de todos os dados pertinentes que seriam necessários para a comunicação de requisitos em um cenário de equipe cruzado em que rede, firewall, criação e gerenciamento de certificados, servidor a implantação e o gerenciamento de servidor são manipulados por grupos diferentes. Ter os detalhes necessários para a configuração de redes, firewalls, portas e protocolos, certificados e servidores é inestimável quando a implantação do Lync Server está em andamento.

**Servidor de borda e o pool de bordas**

![7624717a-ce99-4ae8-A929-2c4d74a2e47d] (images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-A929-2c4d74a2e47d")

**Proxy reverso**

![cf63fc50-2D11-4334-afc8-2d664ba1b6bb] (images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2D11-4334-afc8-2d664ba1b6bb")

**Pool de directors ou diretor**

![56ba29ff-1309-4d5d-bf5c-35372169e947] (images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

