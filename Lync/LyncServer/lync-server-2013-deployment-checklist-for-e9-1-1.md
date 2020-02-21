---
title: 'Lync Server 2013: lista de verificação de implantação para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a8bc7072cb1faa197f733d01eb545a964ed6612
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lista de verificação de implantação para E9-1-1 no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Para planejar com eficácia o 9-1-1 Avançado (E9-1-1), certifique-se de incluir os seguintes requisitos de implantação:

  - Pré-requisitos para implantação do E9-1-1.

  - Etapas necessárias para implantar o E9-1-1.

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>Pré-requisitos de implantação para E9-1-1

Antes de implantar o E9-1-1, você já deve ter implantado seus servidores internos do Lync Server, incluindo um repositório de gerenciamento central, um pool de front-end ou um servidor Standard Edition, um ou mais servidores de mediação ou pools de servidores de mediação e clientes do Lync Server. Além disso, uma implantação do E9-1-1 exige um tronco SIP para um provedor de serviço de E9-1-1 certificado ou um gateway ELIN (Emergency Location Identification Number) para seu PSTN (Rede telefônica comutada pública). O Lync Server suporta o uso de provedores de serviço E9-1-1 apenas dentro dos Estados Unidos.

</div>

<div>

## <a name="deployment-process"></a>Processo de implantação

A tabela a seguir fornece uma visão geral do processo de implantação de E9-1-1. Para obter detalhes sobre etapas de implantação, consulte [Configure enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) na documentação de implantação.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Funções</th>
<th>Documentação de implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Definir utilização de voz, rotas e configurações de tronco</p></td>
<td><ol>
<li><p>Crie um novo registro de uso de PSTN. Este é o mesmo nome utilizado para a configuração de <strong>Uso do PSTN</strong> na política local.</p></li>
<li><p>Crie ou atribua uma rota de voz ao registro de uso do PSTN criado na etapa anterior e aponte o atributo gateway para o tronco SIP ou gateway ELIN de E9-1-1.</p></li>
<li><p>Para um provedor de serviço de E9-1-1 por tronco SIP, configure o tronco que manipulará as chamadas de E9-1-1 sobre o SIP para passar os dados de PIDF-LO usando o cmdlet <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</p></li>
<li><p>Opcionalmente, para um provedor de serviço de E9-1-1 do tronco SIP, crie ou atribua uma rota PSTN local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviço de E9-1-1. Esta rota será usada se a conexão com o provedor de serviço de E9-1-1 não estiver disponível. Se o provedor de serviço de E9-1-1 for suportado, atribua uma regra de configuração de tronco ao gateway que converte a cadeia de caracteres de discagem 911 no número DID (discagem direta interna) do ECRC (Centro de resposta de chamada de emergência) nacional.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurar uma rota de voz do E9-1-1 no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Criar políticas locais e atribuí-las aos usuários e sub-redes</p></td>
<td><ol>
<li><p>Revise a política de de local global.</p></li>
<li><p>Crie uma política local com um escopo no nível do usuário ou no nível do site de rede, se a organização tiver mais de um site com diferentes usos de emergência.</p></li>
<li><p>Atribua a política de local aos sites de rede.</p></li>
<li><p>Adicione as sub-redes apropriadas ao site de rede.</p></li>
<li><p>(Opcional) Atribua a política local às políticas de usuário.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (exceto para a criação de Políticas de Local)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Criar políticas de local no Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Adicionar uma política de local a um site de rede no Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associar sub-redes a sites de rede para o E9-1-1 no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configure o banco de dados de localização</p></td>
<td><ol>
<li><p>Preencha o banco de dados com um mapeamento de elementos de rede para os locais.</p></li>
<li><p>Para gateways ELIN, adicione o ELINs à coluna &lt;CompanyName&gt; .</p></li>
<li><p>Configure a conexão com o provedor de serviço de E9-1-1 para endereços de validação.</p></li>
<li><p>Valide os endereços com o provedor de serviço de E9-1-1.</p></li>
<li><p>Publique o banco de dados atualizado.</p></li>
<li><p>Para gateways ELIN, carregue os ELINs no banco de dados de ALI (Automatic Location Identification) da operadora de seu PSTN.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configurar o banco de dados de localização no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configure os Recursos Avançados (opcional)</p></td>
<td><ol>
<li><p>Configure a URL para o aplicativo SNMP.</p></li>
<li><p>Configure a URL para o local do serviço de informações de local secundário.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Configurar um aplicativo SNMP no Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurar um serviço de informações de local secundário no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

