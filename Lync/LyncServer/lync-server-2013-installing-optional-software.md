---
title: 'Lync Server 2013: Instalando software opcional'
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
ms.openlocfilehash: 2ce81d2005a9bbed5432f2c78f3d8df5507d6679
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Instalando software opcional no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

A ferramenta de planejamento do Microsoft Lync Server 2013 foi projetada para exportar para o Microsoft Excel e o Microsoft Visio. Embora esses aplicativos não sejam necessários para a operação da ferramenta de planejamento, eles adicionam um valor significativo à implantação e à documentação do seu design.

<div>

## <a name="optional-software"></a>Software opcional

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

Exportar seu design para o Microsoft Excel cria um relatório que exibe sete guias na planilha:

  - Resumo – exibe informações sobre a configuração do site, incluindo contagem de usuário, configurações de capacidade e informações de perfil do servidor.

  - Perfil de hardware – Exibe um relatório sobre as configurações de hardware recomendadas para servidores especificados na topologia, incluindo CPU, memória, disco e interface de rede. A quantidade e as especificações recomendadas para os componentes do servidor também estão incluídas. Além disso, cada servidor é definido pelo site para fornecer uma representação completa dos requisitos de servidor por site.

  - Requisitos de portas – exibe um relatório de todas as portas habilitadas e a associação ao balanceamento de carga do sistema de nomes de domínio (DNS LB) e aos balanceadores de carga de hardware (HLB). Você deve usar este relatório para planejar suas configurações de firewall e DNS LB e HLB.

  - Relatório de resumo – exibe o resumo geral das configurações necessárias para configurar sua rede de servidor de borda.

  - Relatório de certificados – exibe o nome da entidade e os nomes alternativos da entidade que são necessários para os certificados necessários para obter os servidores de borda em execução.

  - Relatório de firewall – exibe as portas de origem e de destino e endereços IP para interfaces externas e internas.

  - Relatório DNS – exibe o nome de domínio totalmente qualificado (FQDN) e os endereços IP/VIP necessários para cada entrada DNS que você criar.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

Exportar seu design para o Microsoft Visio cria um diagrama para ser usado com seus objetivos de documentação de sua topologia e infraestrutura configuradas. O diagrama importado pode ser editado e reorganizado a fim de atender às suas necessidades de documentação. O diagrama típico do Visio incluirá:

<div>


> [!NOTE]  
> Se seu design for grande o suficiente para exigir mais de três servidores front-end, uma página adicional será criada para o pool de front-ends, servidores front-end, o computador que executa o SQL Server, endereços IP e FQDNs.



</div>

  - Topologia global – diagrama dos sites do Lync Server 2013 configurados.

  - Guia nome do site – exibe a topologia de configuração do site com o servidor de borda, o firewall, a PSTN (rede telefônica pública comutada) com gateways e a implantação de servidor interno. A implantação interna consiste em servidores e pools configurados, incluindo o pool de front-ends, servidores baseados em SQL Server, serviços de domínio do Active Directory, diretores, servidores de Unificação de mensagens (UM) do Exchange, servidores de caixa de correio do Exchange, servidores do Office Web Apps Servidores de mediação e servidores de chat persistente.

  - Diagrama de rede de borda – diagrama detalhando a configuração do servidor de borda com endereços IP e FQDNs associados. Balanceamento de carga de DNS e balanceadores de carga de hardware também estão incluídos. Além disso, os diretores e o servidor front-end ou o pool de front-ends são exibidos, com o DNS LB ou o HLB associado e o endereço IP atribuído (a ferramenta de planejamento suporta endereços IPv4 e IPv6) e FQDN.

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Instalando a ferramenta de planejamento no Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

