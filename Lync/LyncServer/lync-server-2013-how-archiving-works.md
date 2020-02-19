---
title: 'Lync Server 2013: como o arquivamento funciona'
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
ms.openlocfilehash: 587405b686832aa3240754575962bf8830181a03
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Como o arquivamento funciona no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-04_

O arquivamento do Lync Server 2013 fornece opções para ajudá-lo a atender às suas necessidades de conformidade. Para implementá-lo e mantê-lo de maneira mais eficaz para atender aos requisitos da sua organização, você deve entender:

  - Quais tipos de informações podem ser arquivadas.

  - Como habilitar e desabilitar o arquivamento na sua implantação.

  - As opções de arquivamento que você pode configurar para controlar como o arquivamento será implementado.

<div>

## <a name="what-information-can-be-archived"></a>Quais tipos de informações podem ser arquivadas?

Os seguintes tipos de conteúdo podem ser arquivados:

  - Mensagens instantâneas de ponto a ponto

  - Conferências (reuniões), que são mensagens instantâneas com vários participantes

  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)

  - Os quadros de comunicações e votações compartilhados durante uma conferência

Os seguintes tipos de conteúdo não são arquivados:

  - Transferências de arquivo ponto a ponto

  - Áudio/vídeo para mensagens instantâneas e conferências de ponto a ponto

  - O compartilhamento de área de trabalho e aplicativos para mensagens instantâneas e conferências de ponto a ponto

O Lync Server também não arquiva conversas de chat persistente. Para arquivar conversas de chat persistente, você deve habilitar e configurar o serviço de conformidade, que é um componente que pode ser implantado com o servidor de chat persistente do Microsoft Lync Server 2013. Para obter detalhes, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Como eu começo a utilizar o arquivamento?

O arquivamento é instalado automaticamente em cada Servidor Front-End quando você implanta o servidor, mas o arquivamento não é habilitado até você configurá-lo. Como você deve configurá-lo é determinado pelo modo como você implanta o arquivamento:

  - **Arquivamento usando a integração com o Microsoft Exchange.** Se você tem usuários hospedados no Exchange 2013 e suas caixas de correio foram colocadas em bloqueio in-loco, você pode selecionar a opção para integrar o armazenamento do Lync Server 2013 com o armazenamento do Exchange. Se você escolher a opção de integração com o Microsoft Exchange, use as políticas e configurações do Exchange 2013 para controlar o arquivamento de dados do Lync Server 2013 para esses usuários.

  - **Arquivamento usando os bancos de dados de arquivamento do Lync Server.** Se você tiver usuários que não estão hospedados no Exchange 2013 ou que não tiveram suas caixas de correio colocadas em bloqueio in-loco, ou se você não quiser usar a integração do Microsoft Exchange para qualquer um ou todos os usuários em sua implantação, poderá implantar bancos de dados de arquivamento do Lync Server usando o SQL Server  para armazenar dados de arquivamento para esses usuários. Nesse caso, as configurações e políticas de arquivamento do Lync Server 2013 determinam se o arquivamento está habilitado e como ele é implementado. Para usar o Lync Server 2013, você deve adicionar os bancos de dados do SQL Server apropriados à sua topologia e publicar a topologia.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Configuração de arquivamento ao usar a integração com o Microsoft Exchange

Se os seus usuários estiverem hospedados no Exchange 2013 e suas caixas de correio tiverem sido colocadas em bloqueio in-loco, você poderá escolher a opção de **integração do Microsoft Exchange** (conforme descrito mais adiante nesta seção) para arquivar o Lync Server 2013 para esses usuários e, em seguida, controlar o arquivamento desses usuários especificando as configurações e políticas de bloqueio in-loco do Exchange, bem como as configurações

  - Se arquivará mensagens instantâneas, conferências ou ambas.

  - Se deve implementar o modo crítico para a implantação do Lync Server.

  - Seleção da opção de integração do Microsoft Exchange para usar o Exchange 2013 para armazenamento de dados arquivados.

Essas opções de configuração de arquivamento do Lync Server 2013 são descritas mais adiante nesta seção. Para obter informações sobre como configurar as políticas de bloqueio in-loco do Exchange para dar suporte ao arquivamento, consulte a documentação do produto Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Configuração de arquivamento ao utilizar o armazenamento do banco de dados do Lync Server

Se você quiser usar bancos de dados de arquivamento do Lync Server (usando bancos de dados do SQL Server) para arquivar dados de qualquer usuário em sua implantação, você pode configurar as políticas de arquivamento do Lync Server para controlar se o arquivamento está habilitado para esses usuários. Em cada política de arquivamento, você pode habilitar e desabilitar o arquivamento para uma ou ambas as opções a seguir:

  - Comunicações internas

  - Comunicações externas

Por padrão, o arquivamento não está habilitado para comunicações internas ou comunicações externas em qualquer política de arquivamento do Lync Server. Você habilita e desabilita as comunicações usando o painel de controle do Lync Server 2013 ou usando cmdlets no Shell de gerenciamento do Lync Server 2013.

As políticas de arquivamento do Lync Server 2013 incluem o seguinte:

  - **Política de arquivamento global**. Essa é uma política de arquivamento padrão e se aplica a toda a sua implantação. Ele é criado quando você implanta o Lync Server 2013 e, por padrão, desabilita o arquivamento para comunicações internas e externas. Não é possível excluir essa política. Se você escolher a opção excluir, a política global será redefinida para as configurações padrão.

  - **Política de arquivamento do site**. Opcionalmente, você pode habilitar ou desabilitar o arquivamento para um ou mais sites específicos criando e configurando uma política de arquivamento em nível de site para o site. Quando você criar uma política de arquivamento em nível de site, por padrão, o arquivamento não está ativado. Você pode excluir qualquer política de arquivamento em nível de site que tenha criado. Uma política de arquivamento em nível de site substitui a política global, mas somente para o site especificado na política. Por exemplo, se você habilitar o arquivamento de comunicações internas e externas em sua política global e criar uma política de site na qual você desabilita o arquivamento de comunicações externas, somente as comunicações internas serão arquivadas para esse site.

  - **Política de arquivamento do usuário**. Opcionalmente, você pode habilitar ou desabilitar o arquivamento para um ou mais usuários e grupos de usuários específicos criando, configurando e aplicando uma política de arquivamento em nível de usuário para os usuários e grupos de usuários especificados. Quando você cria uma política de arquivamento em nível de usuário, por padrão, o arquivamento não está habilitado. É possível excluir qualquer política de arquivamento em nível de usuário que você criou e também é possível alterar a quais usuários e grupos de usuários a política de arquivamento se aplica. Uma política de arquivamento em nível de usuário substitui a política global e as políticas do site, mas somente para os usuários e grupos de usuários aos quais a política foi aplicada. Por exemplo, se você desabilitar o arquivamento de comunicações internas e externas em sua política global, crie uma política em nível de site e habilite nela o arquivamento de comunicações internas e externas e, em seguida, crie uma política em nível de usuário e desabilite nela o arquivamento de comunicações externas, as comunicações serão arquivadas para as comunicações internas e externas para todos os usuários do site, exceto para os usuários aos quais você aplicar a política em nível de usuário, somente as comunicações internas seriam arquivadas.

Para obter detalhes sobre como configurar as políticas de arquivamento iniciais ao implantar o arquivamento, consulte [Configuring and atribuição Archiving Policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) na documentação de implantação. Para obter detalhes sobre como usar políticas de arquivamento para habilitar e desabilitar comunicações após a implantação, consulte [Managing the Archiving of Internal and external Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) na documentação operações.

<div>


> [!NOTE]  
> Se você implementar os bancos de dados de arquivamento do Lync Server 2013 e habilitar a integração com o Microsoft Exchange, as políticas do Exchange 2013 substituirão as políticas de arquivamento do Lync Server, mas apenas para os usuários hospedados no Exchange 2013 e tiveram suas caixas de correio colocadas em bloqueio in-loco . O arquivamento do Lync depende apenas da política de bloqueio in-loco do Microsoft Exchange.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Quais opções eu tenho para configurar um arquivamento?

Além de utilizar as políticas e habilitar e desabilitar o arquivamento, você tem outras opções de  arquivamento que podem ser configuradas para toda a sua implantação e, opcionalmente, para sites e pools específicos. Você controla a maioria das opções de arquivamento usando uma ou mais configurações de arquivamento, que estão disponíveis no painel de controle do Lync Server 2013, mas também têm outra opção que só está disponível para configuração usando o Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Opções de configuração de arquivamento disponíveis no Painel de Controle do Lync Server 2013

Cada configuração de arquivamento fornece as seguintes opções:

A configuração em nível global é criada automaticamente quando você implanta o arquivamento e pode ser configurada, mas não excluída. Se você selecionar a opção para excluir a configuração global, as configurações são redefinidas para os valores padrão. Você pode criar várias configurações de site e de pool que, em conjunto com a configuração global, controlam as configurações de arquivamento. Para a configuração global e cada configuração de site e de pool, você tem as seguintes opções:

  - Desabilite o arquivamento, habilite o arquivamento somente para mensagens instantâneas (IM) ou habilite o arquivamento das mensagens instantâneas e das conferências.

  - Configure o modo crítico para bloquear as sessões de IM e conferências no caso de uma falha do Lync Server. As falhas incluem o seguinte:
    
      - **Im**. Um problema com o serviço de armazenamento do Lync Server. Neste caso, as mensagens instantâneas são bloqueadas para os usuários que estiverem habilitados para arquivamento.
    
      - **Conferências**. Uma falha poderia ser um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.

  - Especifique o uso da integração do Microsoft Exchange Server 2013 para usar o Exchange 2013 para armazenamento de dados arquivados, em vez de configurar bancos de dados do SQL Server separados para armazenamento de dados de arquivamento do Lync Server 2013.

  - Configure as opções de limpeza para os dados arquivados. Isso inclui especificar quando limpar os dados arquivados, que pode ser uma das opções a seguir:
    
      - Após um número de dias especifico que você especificou
    
      - Após a exportação dos dados de arquivamento (que inclui dados que foram carregados no Exchange, se você habilitar a integração com o Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Se você habilitar a integração com o Microsoft Exchange, a limpeza para usuários hospedados no Exchange 2013 e em suas caixas de correio colocadas no bloqueio in-loco é controlada pelo Exchange. A única qualificação é para arquivos de conferência, que são armazenados no compartilhamento de arquivos do Lync Server. Esses arquivos são excluídos do compartilhamento de arquivos somente depois que os arquivos foram exportados (carregados no Exchange), se você selecionar a opção para limpar dados após os dados de arquivamento terem sido exportados ou após o número máximo de dias especificado, se você especificar um número máximo de dias para retenção.

    
    </div>

Por padrão, nenhuma opção de arquivamento está habilitada. Você pode gerenciar as configurações de arquivamento usando o painel de controle do Lync Server 2013.

Você pode especificar as seguintes configurações de arquivamento:

  - **Configuração de arquivamento global**. Essa é a configuração de arquivamento padrão e se aplica a toda a sua implantação. Ele é criado quando você implanta o Lync Server 2013 e, por padrão, não habilita a funcionalidade de arquivamento. É possível modificar a configuração global, mas não é possível excluí-la. Se você escolher excluir a opção para a configuração, a configuração global será redefinida para as configurações padrão.

  - **Configuração de arquivamento do site**. Opcionalmente, você pode configurar o arquivamento para um ou mais sites específicos criando e definindo uma configuração em nível de site para um site individual. Uma configuração de arquivamento em nível de site existe somente se você criá-la. É possível modificar e excluir qualquer configuração de arquivamento em nível de site. Uma configuração de arquivamento em nível de site substitui uma configuração global, mas somente para o site especificado na configuração em nível de site. Por exemplo, se você habilitar o arquivamento somente para as mensagens instantâneas na sua configuração global e criar uma configuração de site na qual você habilite o arquivamento para as mensagens instantâneas e conferências, as conferências serão somente arquivadas para o restante da sua organização.

  - **Configuração de arquivamento do pool**. Opcionalmente, você pode especificar as configurações de arquivamento para um ou mais pools específicos criando e definindo uma configuração em nível de pool para um pool individual. Uma configuração de arquivamento em nível de pool existe somente se você criá-la. É possível modificar e excluir qualquer configuração de arquivamento em nível de pool. Uma configuração de arquivamento em nível de pool substitui uma configuração global e qualquer configuração de arquivamento de site que tiver sido criada. Por exemplo, se você habilitar o arquivamento somente para as mensagens instantâneas na sua configuração global, crie uma configuração em nível de site na qual você habilite o arquivamento para as mensagens instantâneas e conferências para o site e, então crie uma configuração em nível de pool na qual você habilite o arquivamento somente para as mensagens instantâneas, as comunicações devem ser arquivadas para mensagens instantâneas e conferências para todos os usuários do site, exceto para os usuários hospedados no pool especificado na configuração em nível de pool. Para todos os outros usuários na sua organização, o arquivamento deveria ser habilitado somente para mensagens instantâneas.

Para obter detalhes sobre como definir as configurações iniciais de arquivamento ao implantar o arquivamento, consulte [Configuring Archiving Options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) na documentação de implantação. Para obter detalhes sobre como usar as políticas de arquivamento para habilitar e desabilitar comunicações após a implantação, consulte [Managing Archiving Configuration Options in Lync Server 2013 for Your Organization, sites e pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) na documentação de operações.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Opções de arquivamento disponíveis somente no Windows PowerShell

Usando o Shell de gerenciamento do Lync Server 2013, você pode usar cmdlets para implementar opções que não estão disponíveis no painel de controle do Lync Server 2013. Essas opções incluem o seguinte:

  - **Arquivar mensagens duplicadas**. Para obter detalhes, consulte [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) e [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) na Documentação de operações.

  - **Exportar dados arquivados**. Para obter detalhes, consulte [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Como eu acesso os dados arquivados?

O acesso aos dados arquivados depende de onde os dados estão armazenados:

  - **Armazenamento do Microsoft Exchange**. Se você escolher a opção de integração do Exchange, o Lync Server deposita o conteúdo de arquivamento no armazenamento 2013 do Exchange para todos os usuários hospedados no Exchange 2013 e que tiveram suas caixas de correio colocadas no bloqueio in-loco. Os dados arquivados são armazenados na pasta itens recuperáveis de caixas de correio do usuário, que geralmente são visíveis para os usuários e só podem ser pesquisados por usuários com uma função de **Gerenciamento de descoberta** do Exchange. O Exchange permite pesquisa e descoberta federada, juntamente com o SharePoint, se estiver implantado. Para obter mais detalhes sobre armazenamento, retenção e descoberta de dados armazenados no Exchange, consulte a documentação do Exchange 2013 e do SharePoint.

  - **Arquivamento do Lync Server**. Se você configurar bancos de dados de arquivamento do Lync Server 2013 para armazenamento de dados do Lync Server, os depósitos do Lync Server fazem o arquivamento de conteúdo nos bancos de dados de arquivamento do Lync Server (bancos de dados do SQL Server) para qualquer usuário que não seja hospedado no Exchange 2013 e que não tenham suas caixas de correio colocadas em Bloqueio in-loco. Esses dados não podem ser pesquisados, mas eles podem ser exportados para formatos que podem ser pesquisados utilizando outras ferramentas. Para obter detalhes sobre como exportar dados armazenados em bancos de dados de arquivamento, consulte [exportando dados arquivados do Lync Server 2013](lync-server-2013-exporting-archived-data.md) na documentação operações.

Para obter mais detalhes sobre como o Lync Server 2013 e o Exchange 2013 funcionam juntos, consulte [Exchange Server and SharePoint Integration Support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) na documentação de suporte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

