---
title: 'Lync Server 2013: implantar a aparência da linha compartilhada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6893dbda1c8f9ecf61319d19a24b896ff67de20b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Implantar a aparência da linha compartilhada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-06-13_

Leia este tópico para aprender a implantar a aparência da linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016. O SLA é um recurso para administrar várias chamadas em um número específico chamado número compartilhado.

Para obter mais informações sobre esse recurso, consulte [planejar a aparência de uma linha compartilhada no Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

A aparência da linha compartilhada (SLA) é um novo recurso do Lync Server 2013, atualização cumulativa de abril de 2016. Para habilitar este recurso, você deve primeiro ter implantado essa atualização cumulativa.

<div>

## <a name="install-shared-line-appearance"></a>Instalar Aparência de Linha Compartilhada

1.  Após o Lync Server 2013, a atualização cumulativa de abril 2016 é implantada, o aplicativo SLA não é habilitado por padrão. Para habilitar o aplicativo, siga as etapas abaixo:
    
    1.  Registrar SLA como um aplicativo de servidor executando o seguinte comando para cada pool:
        
            New-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                            http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                            $true -Priority (Get-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/UserServices').Priority 
        
        onde %FQDN% é o nome de domínio totalmente qualificado do pool.
    
    2.  Execute o seguinte comando para atualizar as funções do RBAC para cmdlets de SLA:
        
            Update-CsAdminRole 
    
    3.  Reiniciar todos os Servidores Front-end (serviço RTCSRV) em todos os pools onde o SLA foi instalado e ativado:
        
        ``` 
         Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Criar um grupo SLA e adicionar usuários a ele

1.  Criar o grupo SLA utilizando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -MaxNumberOfCalls <Number> -BusyOption
                  <BusyOnBusy|Voicemail|Forward> [-Target
                  <TargetUserOrPhoneNumber>]
    
    O cmdlet Set-Cs SlaConfiguration marca a conta SLAGroup1 da conta do Enterprise Voice como uma entidade SLA, e o número de SLAGroup1 transforma-se no número para o grupo SLA. Todas as chamadas para SLAGroup1 tocarão no grupo SLA inteiro.
    
    O exemplo a seguir cria um grupo SLA para um usuário Enterprise Voice existente, SLAGroup1 e usa o número atribuído para SLAGroup1 como número principal de SLA.
    
    O comando define o número máximo de chamadas simultâneas para o novo grupo SLA em 3, e chamadas além desse número ouvirão um sinal de ocupado:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                  -BusyOption BusyOnBusy
    
    Você pode usar Set-Cs SlaConfiguration para criar um novo grupo SLA ou modificar um existente.
    
    <div>
    

    > [!NOTE]  
    > Observe que o que você especificar <CODE>-Identity</CODE> para deve ser uma conta de usuário válida habilitada para Enterprise Voice.

    
    </div>

2.  Adicionar representantes ao grupo utilizando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates):
    
        Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    O exemplo a seguir adiciona um usuário ao grupo SLA. Cada usuário adicionado ao grupo deve ser um usuário habilitado para o Enterprise Voice habilitado:
    
        Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate1@contoso.com
    
    Repita o cmdlet para cada usuário que você deseja adicionar ao grupo. Os usuários podem somente pertencer a um único grupo SLA.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Configuração da Opção Ocupado do grupo SLA

1.  Configurar a Opção Ocupado do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    
    O exemplo a seguir define que as chamadas excedendo o número máximo de chamadas simultâneas serão encaminhadas ao número de telefone 202-555-1234. O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe para a pessoa que receber as chamadas encaminhadas é a mesma que quando você especifica um representante: `sip:<NameofDelegate@domain>`. O outro parâmetro possível para `BusyOption` é `Voicemail`:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
                  -Target tel:+2025551234]

</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Configuração da Opção de Chamada perdida do grupo SLA

1.  Configurar a Opção de Chamada Perdida do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
                  -MissedCallOption <Option> -MissedCallForwardTarget
                  <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    
    O exemplo a seguir especifica que as chamadas perdidas serão encaminhadas para o usuário `sla_forward_number`chamado. As opções válidas para `-MissedCallOption` o parâmetro `Forward`são `BusySignal`, ou `Disconnect`. Se você escolher `Forward`, também deverá incluir o `-MissedCallForwardTarget `parâmetro, com um número de usuário ou de telefone como o destino:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
                  Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
            -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 

</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Remover um representante de um grupo

1.  Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates):
    
        Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    Por exemplo:
    
        Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate3@contoso.com

</div>

<div>

## <a name="delete-an-sla-group"></a>Excluir um grupo SLA

1.  Excluir um grupo SLA utilizando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):
    
    ``` 
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Por exemplo:
    
        Remove-CsSlaConfiguration -Identity SLAGroup1 

</div>

</div>

<span> </span>

</div>

</div>

</div>

