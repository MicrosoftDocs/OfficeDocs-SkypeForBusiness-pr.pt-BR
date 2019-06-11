---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a5bb2b2124b84adeb6a494f6f33ce867f7d416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrar grupos de resposta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-09-23_

Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui a cópia de grupos de agente, filas, fluxos de trabalho, arquivos de áudio e movimentação de objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Lync Server 2013. As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.

<div>


> [!NOTE]  
> Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro. Em particular, os usuários que são agentes de grupo de resposta não terão funcionalidade completa dos novos recursos até serem movidos para o pool do Lync Server 2013.



</div>

Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo do grupo de resposta. O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice. Você pode garantir que o aplicativo do grupo de resposta seja instalado executando o cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de respostas herdadas.



</div>

Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** .

<div>


> [!IMPORTANT]  
> O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para o pool inteiro. Não é possível selecionar grupos, filas ou fluxos de trabalho específicos para migrar.



</div>

Depois de migrar os grupos de resposta, você precisará usar o painel de controle do Lync Server ou cmdlets do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agente, filas e fluxos de trabalho foram movidos com êxito.

Quando você migra grupos de resposta, os grupos de resposta do Lync Server 2010 não são removidos. Ao gerenciar grupos de resposta após a migração usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server, você pode ver os grupos de resposta do Lync Server 2010 e os grupos de resposta do Lync Server 2013. Você deve aplicar atualizações somente aos grupos de resposta do Lync Server 2013. Os grupos de resposta do Lync Server 2010 são mantidos somente para fins de recuperação.

<div>


> [!WARNING]  
> Após a conclusão da migração e os novos grupos de resposta terem sido criados, o painel de controle do Lync Server e o Shell de gerenciamento do Lync Server exibirão as versões do Lync Server 2010 e do Lync Server 2013 de cada grupo de resposta. Não use o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para remover os grupos de resposta do Lync Server 2010. Se você remover um, o grupo de resposta correspondente criado durante a migração deixará de funcionar. Os grupos de resposta do Lync Server 2010 serão removidos quando você encerrar o pool do Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> Recomendamos que você não remova dados de sua implantação anterior até encerrar o pool. Além disso, recomendamos enfaticamente que você exporte os grupos de resposta imediatamente após a migração. Se um grupo de resposta do Lync Server 2010 deve ser removido, você pode restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 sendo executados novamente.



</div>

O Lync Server 2013 introduz um novo recurso de grupo de resposta chamado **tipo de fluxo de trabalho**. O **tipo de fluxo de trabalho** pode ser **gerenciado** ou **não gerenciado**. Todos os grupos de resposta são migrados com o **tipo de fluxo de trabalho** definido como **não gerenciado** e com uma lista de gerentes vazia.

Quando você executa o cmdlet **move-CsRgsConfiguration** , os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão. No entanto, se você precisar reverter para o pool herdado, será necessário executar o cmdlet **move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado.

O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013. Se você planeja consolidar ou dividir os pools durante a migração e a implantação, será necessário planejar quais pools herdados são mapeados para qual Lync Server 2013 pool.

<div>

## <a name="to-migrate-response-group-configurations"></a>Migrar configurações de grupo de resposta

1.  Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha direitos e permissões de administrador equivalentes.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por exemplo:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Depois de migrar grupos de resposta e agentes para o pool do Lync Server 2013, a URL usada pelos agentes para entrar e sair é uma URL do Lync Server 2013 e está disponível no menu **ferramentas** . Lembre os agentes para atualizar todas as referências, como indicadores, para a nova URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para verificar a migração do grupo de resposta usando o painel de controle do Lync Server

1.  Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  No painel de navegação esquerdo, clique em **grupos de resposta**.

4.  Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho no ambiente do Lync Server 2010 estão incluídos na lista.

5.  Clique na guia **fila** e verifique se todas as filas em seu ambiente do Lync Server 2010 estão incluídas na lista.

6.  Clique na guia **grupo** e verifique se todos os grupos de agente no ambiente do Lync Server 2010 estão incluídos na lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Para verificar a migração do grupo de resposta usando o Shell de gerenciamento do Lync Server

1.  Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
        Get-Help <cmdlet name> -Detailed

3.  Execute:
    
        Get-CsRgsAgentGroup

4.  Verifique se todos os grupos de agente no ambiente do Lync Server 2010 estão incluídos na lista.

5.  Execute:
    
        Get-CsRgsQueue

6.  Verifique se todas as filas no ambiente do Lync Server 2010 estão incluídas na lista.

7.  Execute:
    
        Get-CsRgsWorkflow

8.  Verifique se todos os fluxos de trabalho no ambiente do Lync Server 2010 estão incluídos na lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

