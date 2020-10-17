---
title: Migrar grupos de resposta
description: Migrar grupos de resposta.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19da4d39b6f11931bffb5a6e422c2826e7351d69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570317"
---
# <a name="migrate-response-groups"></a>Migrar grupos de resposta

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-09-23_

Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo grupo de resposta no pool do Lync Server 2013. As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.

<div>


> [!NOTE]  
> Embora você possa migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro. Em particular, os usuários que são agentes de grupo de resposta não terão a funcionalidade completa dos novos recursos até que sejam movidos para o pool do Lync Server 2013.



</div>

Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo grupo de resposta. O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice. Você pode garantir que o aplicativo grupo de resposta seja instalado executando o cmdlet **Get-CsService – ApplicationServer** .

<div>


> [!NOTE]  
> Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de resposta herdados.



</div>

Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** .

<div>


> [!IMPORTANT]  
> O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para todo o pool. Não é possível selecionar grupos, filas e fluxos de trabalho específicos para migração.



</div>

Após migrar os grupos de resposta, você precisará usar os cmdlets do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agentes, filas e fluxos de trabalho foram movidos com êxito.

Ao migrar grupos de resposta, os grupos de resposta do Lync Server 2010 não são removidos. Ao gerenciar grupos de resposta após a migração usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server, você pode ver os grupos de resposta do Lync Server 2010 e os grupos de resposta do Lync Server 2013. Você deve aplicar as atualizações somente aos grupos de resposta do Lync Server 2013. Os grupos de resposta do Lync Server 2010 são mantidos apenas para fins de recuperação.

<div>


> [!WARNING]  
> Após a conclusão da migração e os novos grupos de resposta terem sido criados, o painel de controle do Lync Server e o Shell de gerenciamento do Lync Server exibirão as versões do Lync Server 2010 e do Lync Server 2013 de cada grupo de resposta. Não use o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para remover os grupos de resposta do Lync Server 2010. Se você remover um, o grupo de resposta correspondente criado durante a migração deixará de funcionar. Os grupos de resposta do Lync Server 2010 serão removidos quando você encerrar o pool do Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> Recomendamos que você não remova dados da sua implantação anterior até suspender o pool. Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após a migração. Se um grupo de resposta do Lync Server 2010 deve ser removido, você pode restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 em execução novamente.



</div>

O Lync Server 2013 introduz um novo recurso de grupo de resposta chamado **tipo de fluxo de trabalho**. O **Tipo de fluxo de trabalho** pode ser **Gerenciado** ou **Não gerenciado**. Todos os grupos de resposta são migrados com o **Tipo de fluxo de trabalho** definido para **Não gerenciado** e com uma lista Gerenciador vazia.

ao executar o cmdlet **Move-CsRgsConfiguration**, os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool de legado para propósitos de reversão. Entretanto, se for necessária uma reversão para o pool antigo, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para transferir objetos de contato de volta para o pool antigo.

O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013. Se você planeja consolidar ou dividir pools durante sua migração e implantação, precisa planejar quais pools herdados mapeiam para qual Lync Server 2013 pool.

<div>

## <a name="to-migrate-response-group-configurations"></a>Para migrar configurações de grupo de resposta

1.  Faça logon no computador com uma conta membro do grupo RTCUniversalServerAdmins ou com direitos e permissões do administrador equivalentes.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por exemplo:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Após migrar grupos de resposta e agentes para o pool do Lync Server 2013, a URL que os agentes usam para entrar e sair é uma URL 2013 do Lync Server e está disponível no menu **ferramentas** . Lembre os agentes de atualizar qualquer referência, como indicadores, para o novo URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para verificar a migração do Grupo de Resposta usando o Painel de Controle do Lync Server

1.  Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  No painel de navegação à esquerda, clique em **Grupos de Resposta**.

4.  Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho em seu ambiente do Lync Server 2010 estão incluídos na lista.

5.  Clique na guia **fila** e verifique se todas as filas no seu ambiente do Lync Server 2010 estão incluídas na lista.

6.  Clique na guia **grupo** e verifique se todos os grupos de agente no seu ambiente do Lync Server 2010 estão incluídos na lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Para verificar a migração do grupo de resposta usando o Shell de gerenciamento do Lync Server

1.  Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
        Get-Help <cmdlet name> -Detailed

3.  Sejam
    
        Get-CsRgsAgentGroup

4.  Verifique se todos os grupos de agente no seu ambiente do Lync Server 2010 estão incluídos na lista.

5.  Sejam
    
        Get-CsRgsQueue

6.  Verifique se todas as filas no seu ambiente do Lync Server 2010 estão incluídas na lista.

7.  Sejam
    
        Get-CsRgsWorkflow

8.  Verifique se todos os fluxos de trabalho em seu ambiente do Lync Server 2010 estão incluídos na lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

