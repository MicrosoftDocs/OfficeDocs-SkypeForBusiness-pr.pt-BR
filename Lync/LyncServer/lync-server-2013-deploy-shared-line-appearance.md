---
title: 'Lync Server 2013: implantar aparência de linha compartilhada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1523a48b5d9056b1cca532a7edb1c826af841b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Implantar aparência de linha compartilhada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-06-13_

Leia este tópico para saber como implantar a aparência da linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016. O SLA é um recurso para lidar com várias chamadas em um número específico chamado de número compartilhado.

Para obter mais informações sobre esse recurso, consulte [Plan for Shared line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

A aparência de linha compartilhada (SLA) é um novo recurso no Lync Server 2013, atualização cumulativa de abril de 2016. Para habilitar esse recurso, primeiro você deve implantar esta atualização cumulativa.

<div>

## <a name="install-shared-line-appearance"></a>Instalar a aparência da linha compartilhada

1.  Após o Lync Server 2013, a atualização cumulativa de abril de 2016 é implantada, o aplicativo SLA não é habilitado por padrão. Para habilitar o aplicativo, siga as etapas abaixo:
    
    1.  Registre o SLA como um aplicativo de servidor executando o seguinte comando para cada pool:
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        em que% FQDN% é o nome de domínio totalmente qualificado do pool.
    
    2.  Execute o seguinte comando para atualizar as funções RBAC para os cmdlets de SLA:
        ```powershell
        Update-CsAdminRole 
        ```
    3.  Reinicie todos os servidores front-end (serviço RTCSRV) em todos os pools em que o SLA foi instalado e habilitado:
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Criar um grupo de SLA e adicionar usuários a ele

1.  Crie o grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    O cmdlet Set-CsSlaConfiguration marca a conta do Enterprise Voice SLAGroup1 como uma entidade SLA e o número de SLAGroup1 se torna o número do grupo SLA. Todas as chamadas para o SLAGroup1 tocarão todo o grupo de SLA.
    
    O exemplo a seguir cria um grupo de SLA para um usuário existente do Enterprise Voice, SLAGroup1, e usa o número atribuído para SLAGroup1 como o número principal de SLA.
    
    O comando define o número máximo de chamadas simultâneas para o novo grupo de SLA como 3 e para as chamadas que excedem o sinal de ocupado:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Você pode usar set-CsSlaConfiguration para criar um novo grupo de SLA ou modificar um existente.
    
    <div>
    

    > [!NOTE]  
    > Observe que o que você especificar <CODE>-Identity</CODE> para deve ser uma conta de usuário válida habilitada para Enterprise Voice.

    
    </div>

2.  Adicione representantes ao grupo usando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    O exemplo a seguir adiciona um usuário ao grupo SLA. Cada usuário adicionado ao grupo deve ser um usuário habilitado para Enterprise Voice válido:
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    Repita o cmdlet para cada usuário que você deseja adicionar ao grupo. Os usuários só podem pertencer a um único grupo de SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Configurar a opção ocupado do grupo de SLA

1.  Configure a opção ocupado do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    O exemplo a seguir define chamadas que excedem o número máximo de chamadas simultâneas a serem encaminhadas para o número de telefone 202-555-1234. O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe da pessoa que receberá as chamadas encaminhadas será o mesmo que quando você especificar um representante: `sip:<NameofDelegate@domain>`. O outro parâmetro possível para `BusyOption` é `Voicemail`:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Configurar a opção de chamada perdida do grupo de SLA

1.  Configure a opção de chamada perdida do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    O exemplo a seguir especifica que as chamadas perdidas devem ser encaminhadas para o `sla_forward_number`usuário chamado. As opções válidas para `-MissedCallOption` o parâmetro `Forward`são `BusySignal`, ou `Disconnect`. Se escolher `Forward`, você também deve incluir o `-MissedCallForwardTarget` parâmetro, com um número de usuário ou de telefone como o destino:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Remover um representante de um grupo

1.  Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Por exemplo:
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>Excluir um grupo de SLA

1.  Exclua um grupo SLA usando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Por exemplo:
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

