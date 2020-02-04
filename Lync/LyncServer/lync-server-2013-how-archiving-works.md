---
title: 'Lync Server 2013: como funciona o arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca026dcfb9b994353de139b6e10ecd419c9dd165
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Como o arquivamento funciona no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-04_

O arquivamento do Lync Server 2013 fornece opções para ajudá-lo a atender às suas necessidades de conformidade. Para implementá-la e mantê-la de forma que atenda aos requisitos da sua organização de forma mais eficiente, você deve entender:

  - Quais informações podem ser arquivadas.

  - Como habilitar e desabilitar o arquivamento em sua implantação.

  - As opções de arquivamento que você pode configurar para controlar a implementação do arquivamento.

<div>

## <a name="what-information-can-be-archived"></a>Quais informações podem ser arquivadas?

Os seguintes tipos de conteúdo podem ser arquivados:

  - Mensagens instantâneas de ponto a ponto

  - Conferências (reuniões), que são mensagens instantâneas com vários participantes

  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)

  - Os quadros de comunicações e votações compartilhados durante uma conferência

Os seguintes tipos de conteúdo não são arquivados:

  - Transferências de arquivo de ponto a ponto

  - Áudio e vídeo de mensagens instantâneas e conferências de ponto a ponto

  - Compartilhamento de área de trabalho e aplicativos em mensagens instantâneas e conferências de ponto a ponto

O Lync Server também não arquiva conversas de chat persistentes. Para arquivar conversas de chat persistentes, você deve habilitar e configurar o serviço de conformidade, que é um componente que pode ser implantado com o Microsoft Lync Server 2013, servidor de chat persistente. Para obter detalhes, consulte [planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Como começar a usar o arquivamento?

O arquivamento será automaticamente instalado em cada servidor front-end quando você implantar o servidor, mas o arquivamento não estará habilitado até você configurá-lo. A forma de configuração é determinada pelo modo de implantação do arquivamento:

  - **Arquivar usando a integração do Microsoft Exchange.** Se você tiver usuários hospedados no Exchange 2013 e suas caixas de correio tiverem sido colocadas no bloqueio in-loco, você pode selecionar a opção para integrar o armazenamento do Lync Server 2013 com armazenamento do Exchange. Se você escolher a opção de integração do Microsoft Exchange, use as políticas e configurações do Exchange 2013 para controlar o arquivamento dos dados do Lync Server 2013 para esses usuários.

  - **Arquivar usando bancos de dados de arquivamento do Lync Server.** Se você tiver usuários que não são hospedados no Exchange 2013 ou que não tiveram suas caixas de correio em bloqueio in-loco, ou se você não quiser usar a integração do Microsoft Exchange para qualquer um ou todos os usuários da sua implantação, poderá implantar bancos de dados de arquivamento do Lync Server usando o SQL Server  para armazenar dados de arquivamento para esses usuários. Nesse caso, as políticas e as políticas de arquivamento do Lync Server 2013 determinam se o arquivamento está habilitado e como ele é implementado. Para usar o Lync Server 2013, você deve adicionar os bancos de dados do SQL Server apropriados à sua topologia e publicar a topologia.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Configuração de arquivamento ao usar a integração do Microsoft Exchange

Se seus usuários estiverem hospedados no Exchange 2013 e suas caixas de correio tiverem sido colocadas no bloqueio in-loco, você poderá escolher a opção de **integração do Microsoft Exchange** (conforme descrito mais adiante nesta seção) para arquivar o Lync Server 2013 para esses usuários e, em seguida, controlar o arquivamento para esses usuários especificando as políticas e as configurações de retenção in-loco

  - Se deseja arquivar mensagens instantâneas, conferências ou ambos.

  - Se você deseja implementar o modo crítico para a implantação do Lync Server.

  - Seleção da opção de integração do Microsoft Exchange para usar o Exchange 2013 para armazenamento de dados arquivados.

Estas opções de configuração de arquivamento do Lync Server 2013 são descritas posteriormente nesta seção. Para obter informações sobre como configurar políticas e configurações de bloqueio do Exchange in-loco para dar suporte ao arquivamento, consulte a documentação do produto Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Configuração de arquivamento ao usar o armazenamento de banco de dados de arquivamento do Lync Server

Se você quiser usar bancos de dados de arquivamento do Lync Server (usando bancos de dados do SQL Server) para arquivar dados de qualquer usuário na sua implantação, poderá configurar as políticas de arquivamento do Lync Server para controlar se o arquivamento está habilitado para esses usuários. Em cada política de arquivamento, você pode habilitar ou desabilitar o arquivamento para qualquer um dos seguintes ou ambos:

  - Comunicações internas

  - Comunicações externas

Por padrão, o arquivamento não está habilitado para comunicações internas ou comunicações externas em qualquer política de arquivamento do Lync Server. Habilite e desabilite as comunicações usando o painel de controle do Lync Server 2013 ou use cmdlets no Shell de gerenciamento do Lync Server 2013.

As políticas de arquivamento do Lync Server 2013 incluem o seguinte:

  - **Política de arquivamento global**. Esta é a política de arquivamento padrão e se aplica a toda a sua implantação. Ele é criado quando você implanta o Lync Server 2013 e, por padrão, desabilita o arquivamento para comunicações internas e externas. Você não pode excluir esta política. Se você escolher a opção Excluir, a política global será redefinida para as configurações padrão.

  - **Política de arquivamento do site**. Opcionalmente, você pode habilitar ou desabilitar o arquivamento de um ou mais sites específicos criando e configurando uma política de arquivamento no nível do site. Quando você cria uma política de arquivamento de nível de site, por padrão, o arquivamento não está habilitado. Você pode excluir qualquer política de arquivamento de nível de site que criar. Uma política de arquivamento em nível de site substitui a política global, mas somente para o site especificado na política. Por exemplo, se você habilitar o arquivamento para comunicações internas e externas em sua política global e criar uma política de site na qual você desabilite o arquivamento de comunicações externas, somente as comunicações internas serão arquivadas para esse site.

  - **Política de arquivamento de usuários**. Opcionalmente, você pode habilitar ou desabilitar o arquivamento para um ou mais usuários específicos e um grupo de usuários, criando, Configurando e aplicando uma política de arquivamento de nível de usuário para os usuários e grupos de usuários especificados. Quando você cria uma política de arquivamento de nível de usuário, por padrão, o arquivamento não está habilitado. Você pode excluir qualquer política de arquivamento de nível de usuário criada e pode alterar a quais usuários e grupos de usuários a política de arquivamento se aplica. Uma política de arquivamento em nível de usuário substitui a política global e as políticas do site, mas somente para os usuários e grupos de usuários aos quais a política é aplicada. Por exemplo, se você desabilitar o arquivamento de comunicações internas e externas em sua política global, crie uma política de nível de site na qual você habilitou o arquivamento para comunicações internas e externas e, em seguida, crie uma política de nível de usuário na qual você desabilita Arquivamento para comunicações externas, as comunicações serão arquivadas para comunicações internas e externas para todos os usuários do site, exceto para os usuários aos quais você aplicar a política de nível de usuário, somente as comunicações internas serão arquivadas.

Para obter detalhes sobre como configurar as políticas de arquivamento iniciais ao implantar o arquivamento, consulte [configurar e atribuir políticas de arquivamento no Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) na documentação de implantação. Para obter detalhes sobre como usar as políticas de arquivamento para habilitar e desabilitar comunicações após a implantação, consulte [Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) na documentação de operações.

<div>


> [!NOTE]  
> Se você implementar os bancos de dados de arquivamento do Lync Server 2013 e habilitar a integração do Microsoft Exchange, as políticas do Exchange 2013 substituirão as políticas de arquivamento do Lync Server, mas somente para os usuários que estiverem hospedados no Exchange 2013 e tiveram suas caixas de correio colocadas no bloqueio in-loco . O arquivamento do Lync depende somente da política de bloqueio in-loco do Microsoft Exchange.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Quais são as opções que eu tenho para configurar o arquivamento?

Além de usar políticas e habilitar e desabilitar o arquivamento, você tem outras opções de arquivamento que podem ser configuradas para toda a implantação e, opcionalmente, para sites e pools específicos. Você controla a maioria das opções de arquivamento usando uma ou mais configurações de arquivamento, que estão disponíveis no painel de controle do Lync Server 2013, mas também tem outra opção que só está disponível para configuração usando o Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Opções de configuração de arquivamento disponíveis no painel de controle do Lync Server 2013

Cada configuração de arquivamento fornece as seguintes opções:

A configuração de nível global é criada automaticamente quando você implanta o arquivamento e pode ser configurada, mas não excluída. Se você selecionar a opção para excluir a configuração global, as configurações serão redefinidas para os valores padrão. Você pode criar várias configurações de site e de pool que, juntamente com a configuração global, configurações de arquivamento de controle. Para obter a configuração global e cada site e configuração de pool, você tem as seguintes opções:

  - Desative o arquivamento, habilite o arquivamento somente para mensagens instantâneas (IM) ou habilite o arquivamento de mensagens instantâneas e de conferência.

  - Configurar o modo crítico para bloquear as sessões de mensagens instantâneas e de conferência no caso de uma falha do Lync Server. As falhas incluem o seguinte:
    
      - **Mensagem instantânea**. Um problema com o serviço de armazenamento do Lync Server. Nesse caso, IM fica bloqueado por usuários habilitados para Arquivamento.
    
      - **Conferência**. Uma falha poderia ser um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.

  - Especifique o uso da integração do Microsoft Exchange Server 2013 para usar o Exchange 2013 para armazenamento de dados arquivados, em vez de configurar bancos de dados separados do SQL Server para armazenamento de dados de arquivamento do Lync Server 2013.

  - Configurar opções de limpeza para dados arquivados. Isso inclui especificar quando limpar dados arquivados, que podem ser um dos seguintes:
    
      - Após um número específico de dias que você especificar
    
      - Após a exportação dos dados do arquivamento (que inclui dados que foram carregados no Exchange, se você habilitar a integração com o Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Se você habilitar a integração do Microsoft Exchange, a limpeza para os usuários hospedados no Exchange 2013 e nas caixas de correio no bloqueio in-loco será controlada pelo Exchange. A única qualificação é para arquivos de conferência, que são armazenados no compartilhamento de arquivos do Lync Server. Esses arquivos são excluídos do compartilhamento de arquivo somente após serem exportados (carregados no Exchange), se você selecionar a opção para limpar os dados após a exportação dos dados de arquivamento ou após o número máximo de dias especificado, se você especificar um número máximo de dias para retenção.

    
    </div>

Por padrão, nenhuma opção de arquivamento está habilitada. Você pode gerenciar as configurações de arquivamento usando o painel de controle do Lync Server 2013.

Você pode especificar as seguintes configurações de arquivamento:

  - **Configuração de arquivamento global**. Esta é a configuração de arquivamento padrão e se aplica a toda a implantação. Ele é criado quando você implanta o Lync Server 2013 e, por padrão, não habilita a funcionalidade de arquivamento. Você pode modificar a configuração global, mas não pode excluí-la. Se você escolher a opção Excluir para a configuração, a configuração global será redefinida para as configurações padrão.

  - **Configuração de arquivamento de sites**. Opcionalmente, você pode configurar o arquivamento para um ou mais sites específicos criando e configurando uma configuração de arquivamento de nível de site para um site individual. Uma configuração de arquivamento no nível do site existe apenas se você criá-la. Você pode modificar ou excluir qualquer configuração de arquivamento no nível do site. Uma configuração de arquivamento em nível de site substitui a configuração global, mas somente para o site especificado na configuração no nível do site. Por exemplo, se você habilitar o arquivamento para apenas mensagens instantâneas em sua configuração global e criar uma configuração de site na qual você habilitou o arquivamento de mensagens instantâneas e de conferência, a conferência só seria arquivada para o site restante da sua organização.

  - **Configuração de arquivamento de pool**. Opcionalmente, você pode especificar configurações de arquivamento para um ou mais pools específicos, criando e configurando uma configuração de nível de pool para o pool individual. Uma configuração de arquivamento em nível de pool existe apenas se você criá-la. Você pode modificar e excluir qualquer configuração de arquivamento em nível de pool. Uma configuração de arquivamento em nível de pool substitui a configuração global e qualquer configuração de arquivamento de site que você tenha criado. Por exemplo, se você habilitar o arquivamento para apenas mensagens instantâneas em sua configuração global, crie uma configuração no nível do site na qual você habilitou o arquivamento de mensagens instantâneas e de conferência para o site e, em seguida, crie uma configuração no nível do pool na qual você habilitou o arquivamento somente para Mensagens instantâneas, as comunicações serão arquivadas para mensagens instantâneas e conferências para todos os usuários do site, exceto os usuários hospedados no pool especificado na configuração no nível do pool. Para todos os outros usuários da sua organização, o arquivamento seria habilitado somente para mensagens instantâneas.

Para obter detalhes sobre como definir as configurações de arquivamento iniciais ao implantar o arquivamento, consulte [Configurando opções de arquivamento no Lync Server 2013](lync-server-2013-configuring-archiving-options.md) na documentação de implantação. Para obter detalhes sobre como usar as políticas de arquivamento para habilitar e desabilitar comunicações após a implantação, consulte [Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e grupos](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) na documentação de operações.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Opções de arquivamento disponíveis somente no Windows PowerShell

Usando o Shell de gerenciamento do Lync Server 2013, você pode usar cmdlets para implementar as opções que não estão disponíveis no painel de controle do Lync Server 2013. Essas opções incluem o seguinte:

  - **Arquivar mensagens duplicadas**. Para obter detalhes, consulte [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) e [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) na documentação de operações.

  - **Exportar dados arquivados**. Para obter detalhes, consulte [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Como faço para acessar dados arquivados?

O acesso aos dados arquivados depende de onde eles estão armazenados:

  - **Armazenamento do Microsoft Exchange**. Se você escolher a opção de integração do Exchange, o Lync Server deposita o conteúdo de arquivamento na loja do Exchange 2013 para todos os usuários que estão hospedados no Exchange 2013 e que tiveram suas caixas de correio colocadas no bloqueio in-loco. Os dados arquivados são armazenados na pasta de itens recuperáveis de caixas de correio do usuário, o que geralmente é invisível para os usuários e só pode ser pesquisado por usuários com uma função de **Gerenciamento de descoberta** do Exchange. O Exchange permite pesquisa e descoberta federada, juntamente com o SharePoint, se estiver implantado. Para obter mais detalhes sobre armazenamento, retenção e descoberta de dados armazenados no Exchange, consulte a documentação do Exchange 2013 e do SharePoint.

  - **Armazenamento do Lync Server**. Se você configurar bancos de dados de arquivamento do Lync Server 2013 para armazenamento de dados do Lync Server, os depósitos do Lync Server armazenarão conteúdo nos bancos de dados de arquivamento do Lync Server (bancos de dados do SQL Server) para qualquer usuário que não seja hospedado no Exchange 2013 e que não tenham suas caixas de correio colocadas em Bloqueio in-loco. This data is not searchable, but it can be exported to formats that are searchable using other tools. Para obter detalhes sobre como exportar dados armazenados em bancos de dados de arquivamento, consulte [exportando dados arquivados do Lync Server 2013](lync-server-2013-exporting-archived-data.md) na documentação de operações.

Para obter mais detalhes sobre como o Lync Server 2013 e o Exchange 2013 trabalham juntos, consulte [suporte à integração do Exchange Server e do SharePoint no Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) na documentação de suporte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

