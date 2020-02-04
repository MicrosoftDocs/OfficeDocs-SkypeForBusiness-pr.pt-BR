---
title: 'Lync Server 2013: descrições e classes do esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Classes e descrições de esquema no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-30_

Esta seção descreve todas as classes de esquema usadas pelo Lync Server 2013.

<div>

## <a name="schema-classes-and-descriptions"></a>Classes e descrições de esquema


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe</th>
<th>Descrição</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>E-mail-destinatário</p></td>
<td><p>Destinatário de email do Exchange Unified Messaging (UM).</p></td>
<td><p>Essa classe auxiliar é compartilhada com o Exchange UM.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Essa classe é um contêiner para vários contatos de aplicativo e não contém nenhum próprio atributo.</p></td>
<td><p>Novo no Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Essa classe contém a entrada para o ponto de controle de serviço para uma instância de serviços de aplicativos de comunicação unificada (UCAS).</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Essa classe fornece uma associação de um pool específico ao seu serviço de aplicativo.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-ApplicationServer mantém atributos representando configurações para instâncias do serviço de aplicativo.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-arquivo morto (obsoleto)</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-GlobalContainer armazena todas as configurações relacionadas ao arquivamento.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (obsoleto)</p></td>
<td><p>Essa classe representa um único servidor de arquivamento de mensagens instantâneas. Uma instância dessa classe é criada quando um computador é ativado como um servidor de arquivamento de mensagens instantâneas, como um computador com o serviço de arquivamento de mensagens instantâneas instalado.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Essa classe é um contêiner para várias instâncias de diretórios de conferência e não contém nenhum próprio atributo.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Essa classe contém atributos que representam as configurações de um diretório de conferência específico.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>Ponto de controle de serviço genérico (SCP) para especificar o computador como um servidor que executa o Lync Server.</p></td>
<td><p>Novo no Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Essa classe auxiliar mantém as configurações para um banco do Microsoft Lync Web App.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-domínio</p></td>
<td><p>Essa classe contém atributos que definem os domínios configurados do registrador SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Esse contêiner de classe representa um único serviço de borda de acesso. Como um serviço de borda de acesso é implantado na rede de perímetro e os clientes geralmente não permitem o acesso dos serviços de domínio Active Directory da rede de perímetro, as instâncias do serviço de borda de acesso não estão associadas à rede do Active Directory da intranet. Portanto, os proxies de acesso não são registrados automaticamente no AD DS. O administrador deve configurar manualmente a existência de cada instância do serviço de borda do Access no AD DS.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-MCU armazena atributos que representam configurações para servidores de conferência.</p></td>
<td><p>Novo no Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-MediationServer mantém atributos representando configurações para servidores de mediação.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Essa classe auxiliar para o msRTCSIP-Server armazena atributos que representam configurações para servidores SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federação</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-GlobalContainer armazena todas as configurações relacionadas à Federação.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Essa classe contém todas as configurações que se aplicam em toda a implantação do Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (obsoleto)</p></td>
<td><p>Essa classe representa uma única política de reunião do Office Communications Server.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>O objeto de configuração de topologia global local.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Contêiner para armazenar objetos de configuração de topologia global.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Essa classe é um contêiner que representa uma instância de uma regra de normalização de localização.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Essa classe é criada pelo aplicativo atendedor de conferência e mantém os atributos usados para categorizar números de telefone de conferência por região.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Essa classe é um contêiner para várias instâncias de mapeamentos de contatos de local e não contém nenhum próprio atributo.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Essa classe é um contêiner que representa um perfil de local específico.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (obsoleto)</p></td>
<td><p>Essa classe é um contêiner para vários perfis de localização e não contém nenhum próprio atributo.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (obsoleto)</p></td>
<td><p>Essa classe é um contêiner para várias regras de normalização locais e não contém nenhum próprio atributo.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Essa classe representa um único servidor de conferência.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Essa classe contém várias classes msRTCSIP-MCUFactory e não tem nenhum próprio atributo.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Essa classe é um contêiner que representa uma fábrica de servidor de conferência para um único tipo de mídia. Uma instância dessa classe é criada quando o primeiro servidor de conferência para esse tipo e fornecedor específico é ativado.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Essa classe fornece uma associação de um pool específico à sua fábrica do servidor de conferência.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Essa classe contém a entrada para o ponto de controle de serviço para um servidor de mediação.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP – reunião (obsoleto)</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos que representam as configurações de reunião configuráveis.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP – mobilidade</p></td>
<td><p>Contêiner que armazena as configurações de mobilidade global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Essa classe contém atributos que representam as configurações de um único servidor de monitoramento.</p></td>
<td><p>Novo no Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (obsoleto)</p></td>
<td><p>Essa classe é um contêiner que representa uma instância de uma rota de menor custo para um gateway ou conjunto de gateways. Essas informações são usadas por todos os pools ou servidores da empresa que executam o Standard Edition para direcionar chamadas feitas para a rede telefônica pública comutada (PSTN) da maneira mais econômica.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (obsoleto)</p></td>
<td><p>Essa classe é um contêiner para várias rotas de custo mínimo e não contém nenhum próprio atributo.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-políticas (obsoletas)</p></td>
<td><p>Essa classe contém várias classes de política do Lync Server e não tem nenhum próprio atributo.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-pool</p></td>
<td><p>Essa classe representa um único pool do Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>Essa classe contém vários pools do Lync Server e não tem nenhum próprio atributo.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Essa classe representa o ponto de controle pointservice do controle de serviço de um pool. Os usuários hospedados em um pool têm seus atributos msRTCSIP-PrimaryHomeServer apontam para uma instância dessa classe.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-presença</p></td>
<td><p>Contêiner que armazena as configurações de presença global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-registrador</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos que representam as configurações de usuário mantidas pelos servidores de registradores SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (obsoleto)</p></td>
<td><p>Essa classe é um contêiner que representa uma instância de um uso de rota telefônica. Uma classe de uso de rota de telefone consiste em um campo de atributo e um campo de descrição. O campo Attribute define um tipo de uso. O campo Descrição permite que os administradores descrevam o uso para esse atributo na rota do telefone.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (obsoleto)</p></td>
<td><p>Essa classe contém várias instâncias da classe msRTCSIP-RouteUsage e não tem nenhum próprio atributo.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-pesquisa</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos que limitam e controlam o escopo dos resultados da pesquisa.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-servidor</p></td>
<td><p>Essa classe representa um único servidor que executa o Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-serviço</p></td>
<td><p>Essa classe mantém o contêiner de configurações globais e os objetos msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Essa classe contém atributos que representam as configurações de um servidor de conferência confiável.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Essa classe contém várias instâncias da classe msRTCSIP-TrustedMCU e não tem nenhum próprio atributo.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Essa classe contém várias classes msRTCSIP-TrustedProxy e não contém nenhum próprio atributo.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Essa classe é um contêiner que representa um servidor de proxy em execução. Uma instância dessa classe é criada ao ativar um novo servidor proxy em um computador associado ao AD DS.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Essa classe contém atributos que representam as configurações de um servidor confiável.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Essa classe é um contêiner que representa um serviço confiável que é roteável usando um endereço de URI (GRUU) do agente do usuário roteável globalmente. Uma instância dessa classe é criada quando um novo servidor confiável pelo Lync Server é ativado. Este servidor confiável deve estar associado a um domínio do Active Directory.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Confiáveisservices</p></td>
<td><p>Essa classe é um contêiner para vários servidores GRUU e não contém nenhum próprio atributo.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Essa classe contém atributos que representam as configurações para um componente da Web confiável.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Essa classe contém várias instâncias da classe msRTCSIP-TrustedWebComponentServer e não tem nenhum próprio atributo.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (obsoleto)</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos relacionados à comunicação unificada.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>Essa classe mantém o ponto de controle pointservice do controle de serviço para o Internet Information Server (IIS). Ele identifica um servidor como um servidor de componentes Web.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Essa classe fornece uma associação de um pool específico para os componentes Web que o pool irá usar.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Esta classe auxiliar para msRTCSIP-WebComponents mantém atributos representando configurações para componentes Web.</p></td>
<td><p>Novo no Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

