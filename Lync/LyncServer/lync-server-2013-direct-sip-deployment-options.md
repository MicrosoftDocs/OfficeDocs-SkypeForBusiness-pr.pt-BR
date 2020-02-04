---
title: 'Lync Server 2013: Opções de implantação de SIP Direto'
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
ms.openlocfilehash: e88dd5a576e467fbca25e9f467bd168fd6401d17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Opções de implantação de SIP Direto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Este tópico fornece exemplos de topologias para a implantação de conexões SIP diretas.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server autônomo

Se a sua organização usa uma das implantações descritas nesta seção, você pode usar o Lync Server 2013 como a única solução de telefonia para parte ou toda uma organização. Esta seção descreve as seguintes implantações em detalhes:

  - **Implantação incremental:** Essa opção pressupõe que você tenha uma infraestrutura existente de PBX (Exchange Branch Exchange) e pretende introduzir o Enterprise Voice de forma incremental para grupos ou equipes menores em sua organização.

  - **Implantação somente VoIP do Lync Server:** essa opção pressupõe que você está considerando a implantação do Enterprise Voice em um site que não tem uma infraestrutura de telefonia tradicional.

<div>

## <a name="incremental-deployment"></a>Implantação incremental

Em implantação incremental, o Lync Server 2013 é a única solução de telefonia para equipes individuais ou departamentos, enquanto o restante dos usuários em uma organização continua a usar um PBX. Esta estratégia de implantação incremental oferece uma maneira de introduzir a telefonia IP na sua empresa por meio de programas pilotos controlados. Os grupos de usuários cujas necessidades de comunicação são mais bem servidos pela Microsoft Unified Communications são movidos para o Enterprise Voice, enquanto outros usuários permanecem no PBX existente. Os grupos de outros grupos podem ser migrados para o Enterprise Voice, conforme necessário.

A opção incremental será recomendada se você tiver claramente definido os grupos de usuários que têm requisitos de comunicação em comum e que se desejam para gerenciamento centralizado. Essa opção também será eficiente se você tiver equipes ou departamentos que sejam espalhados por áreas geográficas grandes, em que a economia em tarifas de longa distância pode ser importante. Na verdade, essa opção é útil para criar equipes virtuais cujos membros podem ficar espalhados pelo mundo todo. Você pode criar, modificar ou desmanchar essas equipes em resposta rápida para atender às necessidades de negócios.

A figura a seguir mostra a topologia genérica para a implantação do Enterprise Voice atrás de um PBX. Esta é a topologia recomendada para implantação incremental.

**Opção de implantação incremental**

![Diagrama de opções de migração departamental](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opções de migração departamental")

<div>


> [!NOTE]  
> Se você estiver conectando a implantação do Lync Server a um parceiro SIP certificado, um gateway PSTN (rede telefônica pública comutada) entre o servidor de mediação e o PBX não será necessário. Para obter uma lista de parceiros SIP diretos certificados, consulte o site do programa de interoperabilidade <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>da Microsoft Unified Communication em.



</div>

<div>


> [!NOTE]  
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado pelo servidor de mediação.



</div>

Nessa topologia, os departamentos ou grupos de domínio selecionados são habilitados para o Enterprise Voice. Um gateway PSTN conecta o grupo de trabalho habilitado para o protocolo de voz com o protocolo de Internet (VoIP) ao PBX. Os usuários que estão habilitados para o Enterprise Voice, incluindo trabalhadores remotos, se comunicam pela rede IP. Chamadas por usuários do Enterprise Voice para a PSTN e para colegas de trabalho que não estão habilitados para Enterprise Voice são roteadas para o gateway PSTN apropriado. As chamadas de colegas que ainda estão no sistema PBX ou de chamadores no PSTN são roteadas para o gateway PSTN, que encaminha as chamadas para o Lync Server para roteamento.

Há duas configurações recomendadas para conectar a Enterprise Voice a uma infraestrutura PBX existente para interoperabilidade: Enterprise Voice atrás do PBX e do Enterprise Voice na frente do PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice atrás do PBX

Quando o Enterprise Voice é implantado por trás do PBX, todas as chamadas da PSTN chegam no PBX, que roteia chamadas para usuários do Enterprise Voice para um gateway PSTN e chamadas para usuários do PBX para o PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice na frente do PBX

Quando o Enterprise Voice é implantado na frente do PBX, todas as chamadas chegam no gateway PSTN, que roteia chamadas para usuários do Enterprise Voice para o Lync Server e chamadas para usuários do PBX para o PBX. Chamadas para a PSTN dos usuários da Enterprise Voice e PBX são roteadas pela rede IP para o gateway PSTN mais econômico. A tabela a seguir mostra as vantagens e desvantagens desta configuração.

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
<td><p>O PBX manipula todos os dispositivos anteriores.</p></td>
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

O Enterprise Voice oferece novas empresas, e também novos sites do Office para empresas existentes, com a oportunidade de implementar uma solução VoIP completa sem precisar se preocupar com a integração com o PBX ou incorrer à implantação e à manutenção substanciais custos de uma infraestrutura de PBX IP. Esta solução aceita funcionários locais e remotos.

Nesta implantação, todas as chamadas são roteadas pela rede IP. As chamadas para a PSTN são roteadas para o gateway PSTN apropriado. O Lync 2013 ou o Lync Phone Edition funciona como um softphone. O controle de chamada remota não está disponível e é desnecessário porque não há telefones PBX para os usuários controlarem. Os serviços de correio de voz e atendedor automático estão disponíveis por meio da implantação opcional da Unificação de mensagens (UM) do Exchange.

<div>


> [!NOTE]  
> Além da infraestrutura de rede necessária para dar suporte ao Lync Server 2013, uma implantação somente VoIP pode usar um gateway pequeno e qualificado para dar suporte a máquinas de fax e dispositivos analógicos.



</div>

A figura a seguir mostra uma topologia típica para uma implantação somente de VoIP.

**Opção de implantação somente VoIP**

![Opção de implantação do Greenfidle](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opção de implantação do Greenfidle")

<div>


> [!NOTE]  
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado pelo servidor de mediação.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

