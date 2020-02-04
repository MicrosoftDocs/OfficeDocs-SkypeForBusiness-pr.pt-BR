---
title: 'Lync Server 2013: instalação de software opcional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a493fed33fff897ea2cccc2a89c0d55c5b8a8097
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Instalação de software opcional no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

O Microsoft Lync Server 2013, ferramenta de planejamento foi projetado para exportar para o Microsoft Excel e o Microsoft Visio. Embora esses aplicativos não sejam necessários para a operação da ferramenta de planejamento, eles adicionam um valor significativo à implantação e à documentação do seu design.

<div>

## <a name="optional-software"></a>Software opcional

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

Exportar seu design para Microsoft Excel cria um relatório que exibe sete guias na planilha:

  - Resumo - Exibe informações sobre a configuração de site, incluindo conta de usuário, configurações de capacidade e informações sobre o perfil do servidor.

  - Perfil de hardware - Exibe um relatório das configurações de hardware recomendadas para servidores especificados na topologia, incluindo CPU, memória, disco e interface de rede. Também está incluída a quantidade e especificações recomendadas para os componentes do servidor. Cada servidor também é definido por site, para fornecer uma representação completa dos requisitos de servidor por cada site.

  - Requisitos de portas - Exibe um relatório de todas as portas habilitadas, além da associação com DNS LB (balanceamento de carga DNS) e HLB (balanceadores de carga de hardware). Esse relatório deve ser usado para planejar suas configurações de firewall e DNS LB e HLB.

  - Relatório de resumo – exibe o resumo geral das configurações necessárias para configurar sua rede de servidor de borda.

  - Relatório de certificados – mostra o nome do requerente e os nomes alternativos de assunto que são necessários para os certificados necessários para obter os servidores de borda em execução.

  - Relatório do firewall - exibe as portas de origem e destino e endereços IP para as interfaces internas e externas.

  - Relatório de DNS - exibe o nome de domínio totalmente qualificado (FQDN) e endereços IP/VIP requeridos para cada entrada DNS que você criar.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

Exportar seu design para o Microsoft Visio cria um diagrama para ser usado com seus objetivos de documentação de sua topologia e infraestrutura configuradas. O diagrama importado pode ser editado e reorganizado a fim de atender às suas necessidades de documentação. O diagrama típico do Visio incluirá:

<div>


> [!NOTE]  
> Se o seu design for grande o suficiente para exigir mais do que três servidores front-end, uma página adicional será criada para o pool de front-end, servidores front-end, o computador que executa o SQL Server, endereços IP e FQDNs.



</div>

  - Topologia global – diagrama dos sites do Lync Server 2013 configurados.

  - Guia nome do site – exibe a topologia de configuração do site com o servidor de borda, o firewall, a PSTN (rede telefônica pública comutada) com gateways e a implantação de servidor interno. A implantação interna consiste em servidores e pools configurados, incluindo os pools de front-end, servidores baseados no SQL Server, serviços de domínio Active Directory, directors, servidores Exchange Unified Messaging (UM), servidores de caixa de correio do Exchange, servidores do Office Web Apps Servidores de mediação e servidores de chat persistentes.

  - Diagrama de rede de borda – diagrama detalhando a configuração do servidor de borda com endereços IP e FQDNs associados. Balanceamento de carga de DNS e balanceadores de carga de hardware também estão incluídos. Além disso, os diretores e o servidor front-end ou o pool de front-end são exibidos com o DNS LB ou o HLB associado e o endereço IP atribuído (a ferramenta de planejamento oferece suporte aos endereços IPv4 e IPv6) e ao FQDN.

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Instalando a Ferramenta de Planejamento no Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

