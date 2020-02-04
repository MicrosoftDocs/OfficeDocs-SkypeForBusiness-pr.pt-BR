---
title: 'Lync Server 2013: modificar as configurações de configuração de tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a>Modificar as configurações de tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. Essas configurações realizam atividades como especificar:

  - Se o desvio de mídia deve ser ativado nos troncos.

  - As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.

  - Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.

Ao instalar o Microsoft Lync Server 2013, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN). Qualquer uma dessas coleções pode ser modificada posteriormente usando o painel de controle do Lync Server ou o Windows PowerShell.

Ao modificar as configurações de tronco SIP usando o painel de controle do Lync Server, as seguintes opções estão disponíveis para você:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuração de UI</th>
<th>Parâmetro do PowerShell</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>Identidade</p></td>
<td><p>Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.</p></td>
</tr>
<tr class="even">
<td><p>Descrição</p></td>
<td><p>Descrição</p></td>
<td><p>Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).</p></td>
</tr>
<tr class="odd">
<td><p>Máximo de diálogos iniciais suportados</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.</p></td>
</tr>
<tr class="even">
<td><p>Nível de suporte de criptografia</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. A configuração de mídia é definida usando cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-CsMediaConfiguration</a> .</p>
<p>Os valores permitidos são:</p>
<ul>
<li><p>- Obrigatório: Deve se utilizar a criptografia SRTP.</p></li>
<li><p>- Optional: O SRTP será utilizado se o gateway lhe fornecer apoio.</p></li>
<li><p>Não suportado: A encriptação de SRTP não é suportada e, portanto, não será usada.</p></li>
</ul>
<p>SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.</p></td>
</tr>
<tr class="odd">
<td><p>Suporte</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Se definido como <strong>Habilitar envio ao gateway</strong>, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.</p>
<p>Se definido como <strong>Habilitar refer usando controle de chamada terceirizado</strong>, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host. o 3pcc também é conhecido &quot;como controle de terceiros&quot; e ocorre quando um terceiro é usado para conectar um par de chamadores (por exemplo, um operador fazendo uma chamada da pessoa para a pessoa B).</p></td>
</tr>
<tr class="even">
<td><p>Habilitar bypass de mídia</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indica se o bypass de mídia foi habilitado para esse tronco. O bypass de mídia só pode ser habilitado se <strong>Processamento centralizado de mídia</strong> também for habilitado.</p></td>
</tr>
<tr class="odd">
<td><p>Processamento centralizado de mídia</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)</p></td>
</tr>
<tr class="even">
<td><p>Habilitar RTP com trava</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar histórico de encaminhamento de chamada</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar dados de encaminhamento P-Asserted-Identity</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar timer de failover do roteamento de saída</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.</p></td>
</tr>
<tr class="even">
<td><p>Uso associado de PSTNsages</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Conjunto de usos PSTN atribuídos ao tronco.</p></td>
</tr>
<tr class="odd">
<td><p>Número convertido para testar</p></td>
<td><p>Não disponível</p></td>
<td><p>Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.</p></td>
</tr>
<tr class="even">
<td><p>Regras de conversão associadas</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).</p></td>
</tr>
<tr class="odd">
<td><p>Regras de conversão do número chamado</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Conjunto de regras de conversão de número de chamada de saída atribuídas ao tronco.</p></td>
</tr>
<tr class="even">
<td><p>Número de telefone a ser de testado.</p></td>
<td><p>Não disponível</p></td>
<td><p>Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.</p></td>
</tr>
<tr class="odd">
<td><p>Número de chamada</p></td>
<td><p>Não disponível</p></td>
<td><p>Indica que o número de telefone a ser testado é o número do chamador.</p></td>
</tr>
<tr class="even">
<td><p>Número chamado</p></td>
<td><p>N/D</p></td>
<td><p>Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Os cmdlets CsTrunkConfiguration do Lync Server dão suporte a propriedades adicionais não mostradas no painel de controle do Lync Server. Para obter mais informações, consulte o tópico da ajuda para o cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">set-CsTrunkConfiguration</A> .



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Para modificar as configurações de tronco SIP usando o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **Roteamento de voz**e, em seguida, clique em **configuração de tronco**.

2.  Na guia **Configuração de Tronco**, clique duas vezes nas configurações do tronco a ser modificado. Observe que é possível editar somente uma coleção de configurações por vez. Se quiser fazer as mesmas alterações em múltiplas coleções, use Windows PowerShell.

3.  Na caixa de diálogo **Editar Configuração de Tronco**, faça as seleções apropriadas e clique em **OK**.

4.  A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.

5.  Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.

6.  Na caixa de diálogo **painel de controle do Microsoft Lync Server 2013** , clique em **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

