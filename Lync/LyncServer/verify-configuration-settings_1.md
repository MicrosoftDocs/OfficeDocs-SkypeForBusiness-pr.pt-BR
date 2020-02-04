---
title: Verificar as definições da configuração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Verificar as definições da configuração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Depois de mesclar a topologia e executar o cmdlet **Import-CsLegacyConfiguration** , verifique se suas configurações e políticas do Office Communications Server 2007 R2 foram importadas para o Lync Server 2013. A tabela a seguir lista as políticas e configurações que devem ser verificadas.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Políticas e configurações para verificar após a migração


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se você usar essa carga de trabalho:</th>
<th>Verifique essas políticas e configurações:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mensagens instantâneas (IM) e conferência</p></td>
<td><p>Política de presença</p>
<p>Política de conferência</p></td>
</tr>
<tr class="even">
<td><p>Conferência discada</p></td>
<td><p>Números de acesso discado</p>
<p>Planos de discagem</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p>Política de voz</p>
<p>Rotas de voz</p>
<p>Planos de discagem</p>
<p>Configurações de uso de PSTN</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>URLs simples </p></td>
</tr>
<tr class="odd">
<td><p>Usuários externos</p></td>
<td><p>Políticas de acesso externo</p></td>
</tr>
<tr class="even">
<td><p>Archiving</p></td>
<td><p>Política de arquivamento</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Para verificar políticas e configurações

1.  No ambiente do Office Communications Server 2007 R2, anote os nomes dos planos de discagem (anteriormente conhecidos como perfis de localização), números de acesso discado (regiões e números de telefone de acesso do atendente de conferência), rotas de voz e as políticas listadas na tabela anterior, além das URLs usadas para o Communicator Web Access.

2.  No servidor front-end do Lync Server 2013, abra o painel de controle do Lync Server.

3.  Para verificar as políticas de conferência importadas, no painel esquerdo, clique em **conferência**, clique em **política de conferência**e verifique se todas as políticas de conferência no ambiente do Office Communications Server 2007 R2 estão incluídas na lista.
    
    <div>
    

    > [!NOTE]  
    > A política de <STRONG>reunião</STRONG> de versões anteriores do Office Communications Server agora é conhecida como a política de conferência no Lync Server 2013. Além disso, a configuração <STRONG>particpants anônima</STRONG> de versões anteriores do Office Communications Server agora é uma configuração na política de conferência do Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > No Office Communications Server 2007 R2, se a política de conferência não estiver definida como <STRONG>usar por usuário</STRONG>, somente as configurações de política global serão importadas. Nenhuma outra política de conferência é importada nessa situação.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se <STRONG>os participantes anônimos</STRONG> estiverem definidos para <STRONG>impor por usuário</STRONG> em sua política de conferência do Office Communications Server 2007 R2, duas políticas de conferência serão criadas durante a migração: uma com <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> definido como <STRONG>true</STRONG> e outra com <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> definido como <STRONG>false</STRONG>.

    
    </div>

4.  Para verificar os planos de discagem importados, clique em **Roteamento de voz**, clique em **plano de discagem**e verifique se todos os planos de discagem no ambiente do Office Communicator 2007 R2 estão incluídos na lista.
    
    <div>
    

    > [!NOTE]  
    > No Lync Server 2013, os <STRONG>perfis de localização</STRONG> agora são chamados de planos de <STRONG>discagem</STRONG>.

    
    </div>

5.  Para verificar as políticas de voz importadas, clique em **Roteamento de voz**, clique em **política de voz**e verifique se todas as políticas de voz no ambiente do Office Communicator 2007 R2 estão incluídas na lista.
    
    <div>
    

    > [!NOTE]  
    > Se a política de voz não estiver definida como <STRONG>usar por usuário</STRONG> no ambiente do Office Communications Server 2007 R2, somente as configurações de política global serão importadas. Nenhuma outra política de voz é importada nessa situação.

    
    </div>

6.  Para verificar as rotas de voz importadas, clique em **Roteamento de voz**, clique em **rota**e verifique se todas as rotas de voz no ambiente do Office Communicator 2007 R2 estão incluídas na lista.

7.  Para verificar as configurações de uso de PSTN importadas, clique em **Roteamento de voz**, clique em **uso PSTN**e verifique se as configurações de uso PSTN do ambiente do Office Communicator 2007 R2 estão incluídas na lista.

8.  Para verificar as políticas de acesso externo importadas, clique em **Federação e acesso externo**, clique em **política de acesso externo**e verifique se todas as políticas de acesso externo em seu ambiente do Office Communicator 2007 R2 estão incluídas na lista.

9.  Para verificar as políticas de arquivamento, clique em **monitoramento e arquivamento**, clique em **política de arquivamento**e verifique se todas as políticas de arquivamento no ambiente do Office Communications Server 2007 R2 estão incluídas na lista.

10. Abra o Shell de gerenciamento do Lync Server.

11. Para verificar as políticas de presença, na linha de comando, digite o seguinte:
    
        Get-CsPresencePolicy
    
    Olhando o nome no parâmetro **Identity** , verifique se todas as políticas de presença no ambiente do Office Communications Server 2007 R2 foram importadas.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Para verificar políticas e configurações usando cmdlets

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Execute os cmdlets na tabela a seguir para verificar as políticas e configurações.
    
    A sintaxe desses cmdlets é como o seguinte exemplo:
    
        Get-CsConferencingPolicy
    
    Para obter detalhes sobre estes cmdlets, execute:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para esta política ou configuração:</th>
<th>Use este cmdlet:</th>
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
<td><p>Números de acesso discado</p></td>
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

