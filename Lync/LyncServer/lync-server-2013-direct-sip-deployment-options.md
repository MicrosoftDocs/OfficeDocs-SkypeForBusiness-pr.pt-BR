---
title: 'Lync Server 2013: opções de implantação de SIP direto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d3d51c8323ab448951255ac9f7cf8d284896ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Opções de implantação de SIP direto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Este tópico fornece exemplos de topologias para a implantação de conexões SIP diretas.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server autônomo

Se sua organização usa uma das implantações descritas nesta seção, você pode usar o Lync Server 2013 como a única solução de telefonia de parte ou de uma organização. Esta seção descreve as seguintes implantações em detalhes:

  - **Implantação incremental:** Essa opção pressupõe que você tenha uma infraestrutura existente de PBX (central privada de comutação de negócios) e você pretende introduzir o Enterprise Voice de forma incremental para grupos menores ou equipes dentro da sua organização.

  - **Implantação somente VoIP do Lync Server:** essa opção pressupõe que você está pensando em implantar o Enterprise Voice em um site que não tem uma infraestrutura de telefonia tradicional.

<div>

## <a name="incremental-deployment"></a>Implantação incremental

Na implantação incremental, o Lync Server 2013 é a única solução de telefonia para equipes ou departamentos individuais, enquanto o restante dos usuários em uma organização continuam a usar um PBX. Essa estratégia de implantação incremental oferece uma maneira de introduzir a telefonia IP em sua empresa por meio de programas piloto controlados. Os grupos de usuários cujas necessidades de comunicação são mais bem servidas pela comunicação unificada da Microsoft são movidos para o Enterprise Voice, enquanto outros usuários permanecem no PBX existente. Os grupos de gerenciamento adicionais podem ser migrados para o Enterprise Voice, conforme necessário.

A opção incremental é recomendada se você tiver definido claramente os grupos de usuários que têm requisitos de comunicação em comum e que se conservem para o gerenciamento centralizado. Essa opção também é eficaz se você tiver equipes ou departamentos que estão espalhados por áreas geográficas amplas, onde a economia nos encargos de longa distância pode ser significativa. Na verdade, essa opção é útil para criar equipes virtuais cujos membros podem ser espalhados pelo mundo. Você pode criar, modificar ou disband essas equipes em resposta rápida para mudar os requisitos de negócios.

A figura a seguir mostra a topologia genérica para a implantação do Enterprise Voice atrás de um PBX. Esta é a topologia recomendada para implantação incremental.

**Opção de implantação incremental**

![Diagrama de opções de migração departamental](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opções de migração departamental")

<div>


> [!NOTE]  
> Se você estiver conectando sua implantação do Lync Server a um parceiro SIP direto certificado, um gateway PSTN (rede telefônica pública comutada) entre o servidor de mediação e o PBX não é necessário. Para obter uma lista de parceiros de SIP diretos certificados, consulte o site do programa de interoperabilidade aberta do Microsoft Unified Communications em <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.



</div>

<div>


> [!NOTE]  
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado através do servidor de mediação.



</div>

Nesta topologia, os departamentos selecionados ou os grupos de gerenciamento estão habilitados para o Enterprise Voice. Um gateway PSTN vincula o grupo de trabalho habilitado para VoIP (Voice over Internet Protocol) ao PBX. Usuários habilitados para o Enterprise Voice, incluindo funcionários remotos, se comunicam através da rede IP. As chamadas de usuários do Enterprise Voice para o PSTN e para os colegas de trabalho que não estão habilitados para Enterprise Voice são roteadas para o gateway PSTN apropriado. As chamadas de colegas que ainda estão no sistema PBX ou de chamadores no PSTN são roteadas para o gateway PSTN, que encaminha as chamadas para o Lync Server para roteamento.

Há duas configurações recomendadas para conectar o Enterprise Voice a uma infraestrutura de PBX existente para interoperabilidade: Enterprise Voice atrás do PBX e Enterprise Voice na frente do PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice atrás do PBX

Quando o Enterprise Voice é implantado por trás do PBX, todas as chamadas de PSTN chegam no PBX, que roteia chamadas para usuários do Enterprise Voice para um gateway PSTN e chamadas para usuários PBX para o PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice na frente do PBX

Quando o Enterprise Voice é implantado na frente do PBX, todas as chamadas chegam no gateway PSTN, que roteia chamadas para usuários do Enterprise Voice para o Lync Server e chamadas para usuários PBX para o PBX. As chamadas para a PSTN de usuários do Enterprise Voice e PBX são roteadas pela rede IP para o gateway PSTN mais econômico. A tabela a seguir mostra as vantagens e desvantagens dessa configuração.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Vantagens e desvantagens da implantação do Enterprise Voice na frente do PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Vantagens</th>
<th>Desvantagens</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>O PBX ainda atende aos usuários não habilitados para o Enterprise Voice.</p></td>
<td><p>Os gateways existentes podem não oferecer suporte aos recursos ou à capacidade desejados.</p></td>
</tr>
<tr class="even">
<td><p>O PBX trata de todos os dispositivos anteriores.</p></td>
<td><p>Requer um tronco do gateway para o PBX e do gateway para o servidor de mediação. Você pode precisar de mais troncos do provedor de serviços.</p></td>
</tr>
<tr class="odd">
<td><p>Os usuários do Enterprise Voice mantêm os mesmos números de telefone.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Implantação somente VoIP do Lync Server

O Enterprise Voice oferece novos negócios e novos sites do Office para empresas existentes, com a oportunidade de implementar uma solução VoIP completa sem ter que se preocupar com a integração de PBX ou incorrer à implantação e à manutenção substanciais custos de uma infraestrutura IP-PBX. Esta solução oferece suporte a funcionários remotos e no local.

Nesta implantação, todas as chamadas são roteadas pela rede IP. As chamadas para a PSTN são roteadas para o gateway PSTN apropriado. O Lync 2013 ou o Lync Phone Edition serve como softphone. O controle de chamada remota não está disponível e é desnecessário porque não há telefones PBX para que os usuários controlem. Os serviços de caixa postal e atendedor automático estão disponíveis por meio da implantação opcional da Unificação de mensagens (UM) do Exchange.

<div>


> [!NOTE]  
> Além da infraestrutura de rede necessária para oferecer suporte ao Lync Server 2013, uma implantação somente VoIP pode usar um gateway pequeno e qualificado para suportar máquinas de fax e dispositivos analógicos.



</div>

A figura a seguir mostra uma topologia típica para uma implantação somente VoIP.

**Opção de implantação somente VoIP**

![Opção de implantação Greenfidle](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opção de implantação Greenfidle")

<div>


> [!NOTE]  
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado através do servidor de mediação.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

