---
title: 'Lync Server 2013: Definindo seus requisitos para Arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75ed62d577cc6b382509f83e53088973e16b6827
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Definindo seus requisitos para Arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

Se a sua organização deve seguir as normas de conformidade, você pode implantar o arquivamento para habilitar o suporte ao arquivamento para mensagens instantâneas (IM) e conferência (reuniões) do Lync Server 2013. Para obter detalhes sobre o tipo de conteúdo que pode ser arquivado, consulte [visão geral do arquivamento no Lync Server 2013](lync-server-2013-overview-of-archiving.md) na documentação de planejamento.

Para implementar o arquivamento, primeiro você precisa decidir como atender os requisitos da sua organização para arquivamento. Isso exige que você determine o seguinte:

  - **Quando implantar**o arquivamento. Você pode implantar o arquivamento como parte da implantação inicial do Lync Server 2013 ou pode adicioná-lo a uma implantação existente. Implante o arquivamento usando o construtor de topologias para adicioná-lo à sua topologia e, em seguida, publicar a topologia.

  - **Arquivar comunicações internas ou externas ou não**. É possível habilitar o arquivamento de comunicações internas (comunicações entre usuários internos), comunicações externas (comunicações que incluem pelo menos um usuário fora da sua rede interna) ou ambos. É possível especificar essas opções para toda a sua organização ou para sites ou pools específicos. Por padrão, nenhuma dessas opções está habilitada.
    
    <div>
    

    > [!NOTE]  
    > Se você usa a integração do Microsoft Exchange para armazenar dados arquivados, as configurações do Exchange controlam se as comunicações do Lync são arquivadas. Se sua implantação inclui várias florestas, você deve sincronizar as configurações entre o Lync Server e o Exchange. O controle de arquivamento de comunicações internas ou externas só está disponível para a política do Lync. Para o arquivamento integrado ao Exchange, ambos serão arquivados ou não arquivados.

    
    </div>

  - **Por que habilitar**o arquivamento. Você pode habilitar e desabilitar o arquivamento para toda a implantação em um nível global, e pode habilitar e desabilitar o arquivamento para sites e usuários específicos. Em cada um desses níveis, especifique se deseja habilitar o arquivamento de sessões de mensagens instantâneas (ponto a ponto), conferências (reuniões, que são sessões com vários participantes) ou ambas. Por padrão, o arquivamento está desabilitado.

  - **Qual é o arquivamento crítico para os usuários da sua organização**. Se o arquivamento for de missão crítica em sua organização, você poderá especificar que o Lync Server 2013 seja executado no modo crítico, que bloqueia as sessões de mensagens instantâneas e de conferência se o arquivamento falhar. Por exemplo:
    
      - Se o serviço de arquivamento estiver temporariamente impossibilitado de enviar uma mensagem para a fila de banco de dados ou inserir uma mensagem no banco de dados, a funcionalidade de mensagens instantâneas e de conferência será bloqueada para a implantação até que o suporte para arquivamento seja restaurado.
    
      - Se um usuário de conferência carregar um arquivo, mas não for possível copiar o arquivo para o repositório de arquivos de arquivamento, a funcionalidade de conferência será bloqueada na implantação até que o problema seja resolvido, mas a funcionalidade de mensagem instantânea não será bloqueada.
    
    Você pode configurar esta opção no nível global, no nível do site e no nível do pool. Por padrão, o modo crítico não está habilitado.

  - **Se a integração com o Microsoft Exchange deve ser usada**. Essa opção integra o arquivamento de armazenamento com o armazenamento do Exchange 2013 para que os dados arquivados do Lync Server e do Exchange 2013 arquivados sejam armazenados juntos no Exchange. Você pode usar a integração do Microsoft Exchange para armazenamento de dados de arquivamento para usuários que são hospedados no Exchange 2013, se as suas caixas de correio tiverem sido colocadas no bloqueio in-loco. Se você não tiver uma implantação do Exchange 2013 ou se preferir não integrá-la, ou se tiver usuários do Lync que não são hospedados no Exchange 2013, você pode implantar bancos de dados de arquivamento separados usando o SQL Server para armazenar dados armazenados em comunicações do Lync. Você pode configurar a opção de integração do Microsoft Exchange no nível global, nível de site e nível de pool. Por padrão, a integração do Microsoft Exchange não está habilitada.

  - **Como os dados arquivados são gerenciados**. O banco de dados de arquivamento não se destina à retenção de longa duração, e o Lync Server 2013 não fornece uma solução de descoberta eletrônica (pesquisa) para dados arquivados, para que os dados sejam movidos para outro armazenamento. O Lync Server fornece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados e que cria transcrições pesquisáveis dos dados arquivados. Para a política global e para cada política de site e usuário que você criar, você pode habilitar a limpeza de dados e especificar uma das seguintes opções:
    
      - Descartar dados de arquivamento exportados e arquivar dados armazenados após um número específico de dias. O número mínimo de dias que você pode especificar é um dia. O número máximo de dias que você pode especificar é de 2562 dias.
    
      - Limpar somente os dados de arquivamento exportados. Essa opção limpa todos os registros que foram exportados e marcados como seguros para serem excluídos pela ferramenta de exportação de sessão.
    
    Você pode configurar esta opção no nível global, no nível do site e no nível do pool. Por padrão, a eliminação não está habilitada.

Você controla o arquivamento usando os seguintes métodos:

  - **Políticas**de arquivamento. Você usa uma ou mais políticas de arquivamento para habilitar e desabilitar o arquivamento de comunicações internas e externas. Por padrão, nenhum arquivamento está habilitado. Você habilita ou desabilita o arquivamento para comunicações internas, comunicações externas ou ambas em sua implantação usando a política global padrão. Não é possível excluir a política global. Você pode especificar uma ou mais políticas de site opcionais para habilitar ou desabilitar o arquivamento de comunicações internas e externas para sites específicos. Você também pode especificar uma ou mais políticas de usuário para habilitar ou desabilitar o arquivamento para usuários e grupos de usuários específicos. Políticas em nível de usuário substituem políticas de site. Políticas no nível do site substituem as políticas de nível global. As políticas em nível de usuário são implementadas somente para os usuários específicos que estão configurados para usar a política. As conferências e mensagens instantâneas em grupo são arquivadas apenas se uma política de pelo menos um dos participantes estiver configurada para habilitar o arquivamento.
    
    <div>
    

    > [!NOTE]  
    > Se você usa a integração do Microsoft Exchange, as políticas do Exchange 2013 substituem as políticas de arquivamento do Lync Server para todos os usuários hospedados nos servidores Exchange 2013.

    
    </div>

  - **Configurações**de arquivamento. Você usa uma ou mais configurações de arquivamento para especificar a maioria das opções de arquivamento descritas anteriormente neste tópico, exceto para habilitar o arquivamento de comunicações internas e externas (configuradas usando políticas de arquivamento, conforme descrito no marcador anterior). As configurações de arquivamento incluem a configuração global padrão e as configurações de site e de pool opcionais. Não é possível excluir a configuração global. Configurações em nível de pool substituem configurações no nível do site. As configurações no nível do site substituem a configuração global de nível global.

Como parte da sua análise de requisitos, você precisa determinar como configurar a configuração de arquivamento global e a política de arquivamento global. Você também precisa determinar suas necessidades para qualquer configuração de arquivamento no nível do site, configurações de arquivamento em nível de pool, políticas de arquivamento em nível de site e políticas de arquivamento em nível de usuário.

Se você implantar o arquivamento para um pool de front-end ou um servidor Standard Edition, habilite-o para todos os outros pools de front-end e servidores Standard Edition na sua implantação. Você precisa fazer isso porque os usuários cujas comunicações são necessárias para serem arquivadas podem ser convidados para uma conversa de mensagem instantânea em grupo ou reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool em que a conversa ou reunião estiver hospedada, todos os dados de conferência podem não ser arquivados. O arquivamento ainda funcionará para o arquivamento de usuários habilitados e todas as mensagens INSTANTÂNEAs, mas o conteúdo da conferência e os eventos podem não ser arquivados.

<div>


> [!NOTE]  
> Para habilitar a delegação de tarefas administrativas enquanto mantém os padrões de segurança da sua organização,&nbsp;o Lync Server 2013 usa o controle de acesso baseado em função (RBAC). Com o RBAC, o privilégio administrativo é concedido com a atribuição de usuários às funções administravas predefinidas. Para configurar as políticas de arquivamento e as configurações de arquivamento do Lync, o usuário deve ser atribuído à função CsArchivingAdministrator (a menos que a configuração seja feita diretamente no servidor em que o arquivamento é implantado, em vez de em outro computador remotamente). Para obter detalhes sobre o RBAC, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejar o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento. Para obter uma lista de direitos de usuário, permissões e funções necessárias para o arquivamento de implantação, consulte <A href="lync-server-2013-deployment-checklist-for-archiving.md">lista de verificação de implantação para arquivamento no Lync Server 2013</A>, que está disponível na documentação de planejamento e na documentação de implantação.<BR>Se você usa a integração do Microsoft Exchange, a configuração das políticas do Exchange exige direitos e permissões de administrador adequados. Para obter detalhes, consulte a documentação do Exchange 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

