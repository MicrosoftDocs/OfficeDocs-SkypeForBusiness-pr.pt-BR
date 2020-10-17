---
title: Verifique as configurações
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508408"
---
# <a name="verify-configuration-settings"></a>Verifique as configurações

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Após mesclar a topologia e executar o cmdlet **Import-CsLegacyConfiguration** , verifique se as políticas e configurações do Office Communications Server 2007 R2 foram importadas para o Lync Server 2013. A tabela a seguir lista as políticas e configurações que você deve verificar.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Políticas e configurações para verificar após a migração


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se você usar esta carga de trabalho:</th>
<th>Verifique estas políticas e configurações:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM (mensagens instantâneas) e conferências</p></td>
<td><p>Política de presença</p>
<p>Política de conferência</p></td>
</tr>
<tr class="even">
<td><p>Conferência Discada</p></td>
<td><p>Números de acesso de discagem</p>
<p>Planos de discagem</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p>Política de voz</p>
<p>Roteamentos de voz</p>
<p>Planos de discagem</p>
<p>Configurações de uso do PSTN</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>URLs simples</p></td>
</tr>
<tr class="odd">
<td><p>Usuários externos</p></td>
<td><p>Políticas de acesso externo</p></td>
</tr>
<tr class="even">
<td><p>Arquivamento</p></td>
<td><p>Política de arquivamento</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Para verificar as políticas e configurações

1.  Em seu ambiente do Office Communications Server 2007 R2, anote os nomes dos planos de discagem (anteriormente conhecidos como perfis de local), números de acesso de discagem (números de telefone e regiões de acesso do atendedor de conferência), rotas de voz e as políticas listadas na tabela anterior, além das URLs usadas para o Communicator Web Access.

2.  No servidor front-end do Lync Server 2013, abra o painel de controle do Lync Server.

3.  Para verificar as políticas de conferência importadas, no painel esquerdo, clique em **conferência**, em **política de conferência**e verifique se todas as políticas de conferência no seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.
    
    <div>
    

    > [!NOTE]  
    > A política de <STRONG>reunião</STRONG> de versões anteriores do Office Communications Server agora é conhecida como a política de conferência no Lync Server 2013. Além disso, a configuração <STRONG>particpants anônima</STRONG> de versões anteriores do Office Communications Server agora é uma configuração na política de conferência do Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > No Office Communications Server 2007 R2, se a política de conferência não estiver definida para <STRONG>uso por usuário</STRONG>, somente as configurações de política global serão importadas. Nenhuma outra política de conferência é importada nessa situação.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se <STRONG>os participantes anônimos</STRONG> estiverem configurados para <STRONG>impor por usuário</STRONG> em sua política de conferência do Office Communications Server 2007 R2, duas políticas de conferência são criadas durante a migração: uma com <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> definido como <STRONG>true</STRONG> e uma com <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> definido como <STRONG>false</STRONG>.

    
    </div>

4.  Para verificar planos importados, clique em **Roteamento de voz**, clique em **Plano de discagem** e, então, verifique se todos os planos de discagem no seu ambiente Office Communicator 2007 R2 estão incluídos na lista.
    
    <div>
    

    > [!NOTE]  
    > No Lync Server 2013, os <STRONG>perfis de local</STRONG> agora são chamados de planos de <STRONG>discagem</STRONG>.

    
    </div>

5.  Para verificar políticas de voz importadas, clique em **Roteamento de voz**, clique em **Política de voz** e, então, verifique se todas as suas políticas de voz do ambiente Office Communicator 2007 R2 estão incluídas na lista.
    
    <div>
    

    > [!NOTE]  
    > Se a política de voz não estiver configurada para <STRONG>uso por usuário</STRONG> no seu ambiente do Office Communications Server 2007 R2, somente as configurações de política global serão importadas. Nenhuma outra política de voz é importada nesta situação.

    
    </div>

6.  Para verificar rotas de voz importadas, clique em **Rota de voz**, clique em **Rota** e, então, verifique se todas as rotas de voz no seu ambiente Office Communicator 2007 R2 estão incluídas na lista.

7.  Para verificar configurações de uso do PSTN, clique em **Roteamento de voz**, clique em **Uso do PSTN** e, então, verifique se as configurações de Uso do PSTN do seu ambiente Office Communicator 2007 R2 foram incluídas na lista.

8.  Para verificar políticas de acesso externo importadas, clique em **Federação e acesso externo**, clique em **Política de acesso externo** e, então, verifique se todas as políticas de acesso externo no seu ambiente Office Communicator 2007 R2 estão incluídas na lista.

9.  Para verificar as políticas de arquivamento, clique em **monitoramento e arquivamento**, em **política de arquivamento**e verifique se todas as políticas de arquivamento no seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.

10. Abra o Shell de Gerenciamento do Lync Server.

11. Para verificar as políticas de presença, na linha de comando, digite o seguinte:
    
        Get-CsPresencePolicy
    
    Olhando o nome no parâmetro **Identity** , verifique se todas as políticas de presença no ambiente do Office Communications Server 2007 R2 foram importadas.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Para verificar as políticas e configurações usando cmdlets

1.  Abra o Shell de Gerenciamento do Lync Server.

2.  Execute os cmdlets na tabela a seguir para verificar as políticas e configurações.
    
    A sintaxe desses cmdlets é como o exemplo abaixo:
    
        Get-CsConferencingPolicy
    
    Para detalhes sobre esses cmdlets, execute:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para essa política ou configuração:</th>
<th>Utilize este cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Política de presença</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Política de conferência</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>Números de acesso de discagem</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Planos de discagem</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>Política de voz</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Rotas de voz</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>Uso de PSTN</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URLs</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>Políticas de acesso externo</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Política de arquivamento</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

