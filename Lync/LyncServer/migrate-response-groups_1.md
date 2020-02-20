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
ms.openlocfilehash: d5433304af6d88ab6eb8a043bbff69b3718faee5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrar grupos de resposta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho e arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo grupo de resposta no pool do Lync Server 2013. As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.

<div>


> [!NOTE]  
> Embora você possa migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro. Em particular, os usuários que são agentes de grupo de resposta não terão a funcionalidade completa dos novos recursos até que sejam movidos para o pool do Lync Server 2013.



</div>

Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo grupo de resposta. O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice. Você pode garantir que o aplicativo grupo de resposta seja instalado executando o cmdlet **Get-CsService – ApplicationServer** .

<div>


> [!NOTE]  
> Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de resposta herdados.



</div>

Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** . Para poder executar o **Move-CsRgsConfiguration**, primeiro você precisa instalar o pacote de interfaces de compatibilidade com versões anteriores WMI (Instrumentação de Gerenciamento do Windows). Instale esse aplicativo executando o OCSWMIBC.msi. Você pode encontrar o OCSWMIBC.msi na pasta Setup da mídia de instalação.

<div>


> [!IMPORTANT]  
> O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para todo o pool. Não é possível selecionar grupos, filas e fluxos de trabalho específicos para migração.



</div>

Após migrar os grupos de resposta, você precisará atualizar a URL que os agentes formais usam para entrar e sair de seus grupos de resposta e usar o painel de controle do Lync Server ou cmdlets do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agentes, filas e fluxos de trabalho foram movidos com êxito.

<div>


> [!WARNING]  
> Ao migrar grupos de resposta, os grupos de resposta do Office Communications Server 2007 R2 não são removidos. Não remova os grupos de resposta do Office Communications Server 2007 R2. Se você remover um grupo de resposta do Office Communications Server 2007 R2, os grupos de resposta no Lync Server 2013 param de funcionar.



</div>

<div>


> [!IMPORTANT]  
> Recomendamos que você não remova dados da sua implantação anterior até suspender o pool. Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após a migração. Se um grupo de resposta do Office Communications Server 2007 R2 for removido, você poderá restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 em execução novamente.



</div>

Quando você executa o cmdlet **Move-CsRgsConfiguration**, as filas, os fluxos de trabalho, os arquivos de áudio e os grupos de agente continuam no pool antigo para fins de reversão. Entretanto, se for necessária uma reversão para o pool antigo, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para transferir objetos de contato de volta para o pool antigo.

<div>


> [!IMPORTANT]  
> Recomendamos que você não exclua dados de grupos de resposta do pool antigo até suspendê-lo.



</div>

O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013. Se você planeja consolidar ou dividir pools durante sua migração e implantação, precisa planejar quais pools herdados mapeiam para qual Lync Server 2013 pool.

<div>

## <a name="to-migrate-response-group-configurations"></a>Para migrar configurações de grupo de resposta

1.  Localize o OCSWMIBC.msi na pasta Setup da mídia de instalação e instale-o.

2.  Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha direitos e permissões de administrador equivalentes.

3.  Abra o Shell de Gerenciamento do Lync Server.

4.  Na linha de comando, digite o seguinte:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Por exemplo:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Se você implantou a guia grupo de resposta do Microsoft Office Communicator 2007 R2 no seu ambiente do Office Communications Server 2007 R2, remova a guia do arquivo Tabs. XML do Office Communicator 2007 R2.
    
    <div>
    

    > [!NOTE]  
    > Agentes formais usavam a guia Grupo de Resposta para fazer logon em seus grupos de resposta antes de poderem receber chamadas. Se você implantou a guia grupo de resposta, você escolheu o local para o arquivo Tabs. XML do Office Communicator 2007 R2 quando o implantou.

    
    </div>

6.  Forneça aos usuários a URL atualizada que os os agentes precisam para fazer logon e sair de seus grupos de resposta.
    
    <div>
    

    > [!NOTE]  
    > A URL normalmente https://webpoolFQDN/RgsClients/Tab.aspxé, onde webpoolFQDN é o nome de domínio totalmente qualificado (FQDN) do pool da Web associado ao pool que você migrou para o Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Esta etapa não é necessária depois que os usuários atualizam para o Lync 2013 porque a URL está disponível no menu <STRONG>ferramentas</STRONG> no Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Para verificar a migração do grupo de resposta usando o painel de controle do Lync Server

1.  Abra o painel de controle do Lync Server.

2.  No painel de navegação à esquerda, clique em **Grupos de Resposta**.

3.  Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

4.  Clique na guia **fila** e verifique se todas as filas em seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.

5.  Clique na guia **grupo** e verifique se todos os grupos de agente em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Para confirmar a migração do grupo de resposta usando o cmdlets

1.  Abra o Shell de Gerenciamento do Lync Server.
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
        Get-Help <cmdlet name> -Detailed

2.  Na linha de comando, digite o seguinte:
    
        Get-CsRgsAgentGroup

3.  Verifique se todos os grupos de agente em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

4.  Na linha de comando, digite o seguinte:
    
        Get-CsRgsQueue

5.  Verifique se todas as filas em seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.

6.  Na linha de comando, digite o seguinte:
    
        Get-CsRgsWorkflow

7.  Verifique se todos os fluxos de trabalho em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.

</div>

</div>

<span> </span>

</div>

</div>

</div>

