---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrar grupos de resposta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho e arquivos de áudio, além de mover objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Lync Server 2013. As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.

<div>


> [!NOTE]  
> Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro. Em particular, os usuários que são agentes de grupo de resposta não terão funcionalidade completa dos novos recursos até serem movidos para o pool do Lync Server 2013.



</div>

Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo do grupo de resposta. O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice. Você pode garantir que o aplicativo do grupo de resposta seja instalado executando o cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de respostas herdadas.



</div>

Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** . Antes de executar **move-CsRgsConfiguration**, você deve primeiro instalar o pacote de interfaces de compatibilidade com versões anteriores do Windows Management Instrumentation (WMI). Instale esse aplicativo executando OCSWMIBC. msi. Você pode encontrar o OCSWMIBC. msi na mídia de instalação na pasta de instalação.

<div>


> [!IMPORTANT]  
> O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para o pool inteiro. Não é possível selecionar grupos, filas ou fluxos de trabalho específicos para migrar.



</div>

Depois de migrar os grupos de resposta, você precisa atualizar a URL que os agentes formais usam para entrar e sair de seus grupos de resposta e usar o painel de controle do Lync Server ou cmdlets do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agente, filas e fluxos de trabalho foram movidos com êxito.

<div>


> [!WARNING]  
> Quando você migra grupos de resposta, os grupos de resposta do Office Communications Server 2007 R2 não são removidos. Não remova os grupos de resposta do Office Communications Server 2007 R2. Se você remover um grupo de resposta do Office Communications Server 2007 R2, os grupos de resposta no Lync Server 2013 param de funcionar.



</div>

<div>


> [!IMPORTANT]  
> Recomendamos que você não remova dados de sua implantação anterior até encerrar o pool. Além disso, recomendamos enfaticamente que você exporte os grupos de resposta imediatamente após a migração. Se um grupo de resposta do Office Communications Server 2007 R2 for removido, você poderá restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 sendo executados novamente.



</div>

Quando você executa o cmdlet **move-CsRgsConfiguration** , os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão. No entanto, se você precisar reverter para o pool herdado, será necessário executar o cmdlet **move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado.

<div>


> [!IMPORTANT]  
> Recomendamos que você não exclua dos dados do grupo de resposta do pool herdado até encerrar o pool.



</div>

O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013. Se você planeja consolidar ou dividir os pools durante a migração e a implantação, será necessário planejar quais pools herdados são mapeados para qual Lync Server 2013 pool.

<div>

## <a name="to-migrate-response-group-configurations"></a>Migrar configurações de grupo de resposta

1.  Localize OCSWMIBC. msi na pasta Setup da mídia de instalação e instale-o.

2.  Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha direitos e permissões de administrador equivalentes.

3.  Abra o Shell de gerenciamento do Lync Server.

4.  Na linha de comando, digite o seguinte:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por exemplo:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Se você implantou a guia grupo de resposta do Microsoft Office Communicator 2007 R2 em seu ambiente do Office Communications Server 2007 R2, remova a guia do arquivo tabulares. XML do Office Communicator 2007 R2.
    
    <div>
    

    > [!NOTE]  
    > Agentes formais usaram a guia grupo de resposta para entrar em seus grupos de resposta antes de poderem receber chamadas. Se você implantou a guia grupo de resposta, você escolheu o local do arquivo tabular. XML do Office Communicator 2007 R2 quando a implantou.

    
    </div>

6.  Forneça aos usuários a URL atualizada que os agentes precisam entrar e sair de seus grupos de resposta.
    
    <div>
    

    > [!NOTE]  
    > A URL geralmente https://webpoolFQDN/RgsClients/Tab.aspxé, em que webpoolFQDN é o nome de domínio totalmente qualificado (FQDN) do pool da Web que está associado ao pool que você migrau para o Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Esta etapa não é necessária após a atualização dos usuários para o Lync 2013 porque a URL está disponível no menu <STRONG>ferramentas</STRONG> do Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para verificar a migração do grupo de resposta usando o painel de controle do Lync Server

1.  Abra o painel de controle do Lync Server.

2.  No painel de navegação esquerdo, clique em **grupos de resposta**.

3.  Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

4.  Clique na guia **fila** e verifique se todas as filas no ambiente do Office Communications Server 2007 R2 estão incluídas na lista.

5.  Clique na guia **grupo** e verifique se todos os grupos de agente no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Para verificar a migração do grupo de resposta usando cmdlets

1.  Abra o Shell de gerenciamento do Lync Server.
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
        Get-Help <cmdlet name> -Detailed

2.  Na linha de comando, digite o seguinte:
    
        Get-CsRgsAgentGroup

3.  Verifique se todos os grupos de agente no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

4.  Na linha de comando, digite o seguinte:
    
        Get-CsRgsQueue

5.  Verifique se todas as filas no ambiente do Office Communications Server 2007 R2 estão incluídas na lista.

6.  Na linha de comando, digite o seguinte:
    
        Get-CsRgsWorkflow

7.  Verifique se todos os fluxos de trabalho no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

