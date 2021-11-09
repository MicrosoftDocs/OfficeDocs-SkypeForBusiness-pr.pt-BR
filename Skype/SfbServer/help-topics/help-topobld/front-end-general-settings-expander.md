---
title: Expansor de Configurações Gerais de Front End
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Para editar as configurações de um pool Front-End existente ou servidor Standard Edition, as seguintes seções são disponibilizadas:'
ms.openlocfilehash: 60e6099cb28ec564abde9506afb1a0ef70274684
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861448"
---
# <a name="front-end-general-settings-expander"></a>Expansor de Configurações Gerais de Front-end

Para editar as configurações de um pool Front-End existente ou servidor Standard Edition, as seguintes seções são disponibilizadas:

- Configurações gerais

- Configurações de resiliência

- Configurações de serviços web

- Configurações de Servidor de Mediação

## <a name="front-end-pool"></a>Pool de Front-Ends

Para um pool de Front-Ends, é possível definir configurações gerais, de resiliência, serviços Web e do Servidor de Mediação. Para obter detalhes, consulte as informações nas subseções a seguir. Para obter detalhes sobre como definir as configurações para o pool de Front-Ends, consulte [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).

### <a name="general-settings"></a>Configurações Gerais

É possível definir as seguintes configurações gerais:

- **FQDN**. Edite o FQDN do pool para alterá-lo.

- **Habilitar porta de monitoramento do Balanceador de Carga de Hardware**. Marque a caixa de seleção e digite o número de porta que seu Balanceador de carga de hardware usará para monitorar o estado dos servidores de pool.

- Em **Recursos e Funcionalidade**, defina as funções adicionais que você deseja colocar com esse pool. É possível definir as seguintes configurações:

  - **Conferência**. Inclui áudio, vídeo e compartilhamento de aplicativos. Após selecionar esta opção, você pode selecionar conferência discada (PSTN). Você especifica e define um gateway de PSTN (rede telefônica pública comutada) na subseção "Configurações de Servidor Mediação" mais tarde nesta seção.

  - **Enterprise Voice**. Habilita chamadas internas de voz sobre IP a dispositivos e dispositivos qualificados e Skype for Business clientes. Para habilitar os recursos de chamada externa, é necessário incluir um Servidor de Mediação. Para obter detalhes, consulte "Servidor de Mediação" posteriormente neste tópico.

- Em **Associações**, edite ou especifique o seguinte:

  - **SQL Store**. Modifique um banco de dados do SQL Server existente ou crie um novo banco de dados baseado em SQL Server para armazenar os bancos de dados do pool Front-Ends. É possível selecionar uma nova instância do SQL Server a partir da lista ou criar uma nova entrada clicando em **Novo**.

    Selecione **Habilitar espelhamento do repositório do SQL Server** e selecione o servidor a ser usado para o espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.

    Selecione **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar um servidor a ser usado como uma testemunha de espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.

  - **Compartilhamento de arquivo**. Modifique o repositório de arquivo usado pelo pool de Front-Ends. É possível selecionar um novo repositório de arquivo entre aqueles já definidos, selecionando-o na lista. É possível criar um novo repositório de arquivo clicando em **Novo**.

    > [!IMPORTANT]
    > Antes de publicar a topologia recém-definida, o servidor especificado precisa existir e fazer parte do domínio.

  - **Arquivamento**. Associe um repositório do Servidor de Arquivamento ao pool de Front-Ends. É possível selecionar um repositório do SQL Server de Arquivamento já definido selecionando o servidor na lista, ou clique em **Novo** para especificar um novo Servidor de Arquivamento.

    > [!IMPORTANT]
    > Antes de publicar a topologia recém-definida, o servidor especificado precisa existir e fazer parte do domínio.

    Selecione **Habilitar espelhamento do repositório do SQL Server** e selecione o servidor a ser usado para espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.

    Selecione **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar um servidor para usar como uma testemunha de espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.

  - **Monitoramento (métricas de CDR e QoE)**. Selecione para associar um repositório do SQL Server de Monitoramento ao pool de Front-Ends. É possível selecionar um Servidor de Monitoramento já definido, selecionando-o na lista,, ou clicar em **Novo** para especificar um novo Servidor de Monitoramento.

    Selecione **Habilitar espelhamento de repositório do SQL Server** e selecione o servidor a ser usado para espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.

    Selecione **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar um servidor para usar como uma testemunha de espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.

  - **Associar pool de Borda (para componentes de mídia)**. Associe um Servidor de Borda ou pool ao pool de Front-Ends. É possível selecionar um Servidor de Borda ou pool já definido selecionando o servidor na lista, ou clique em **Novo** para especificar um novo Servidor de Borda ou pool.

  - **Associar pool a um Office Web Apps Server**. Selecione essa opção para associar um Office Web Apps Server ao pool de Front-Ends. Selecione um servidor existente na lista, ou clique em **Novo** para criar um novo Office Web Apps Server.

### <a name="resiliency"></a>Resiliência

Resiliência fornece recuperação de desastre e alta disponibilidade para o pool. Ao fornecer um backup, se o servidor primário falhar, o servidor de backup poderá assumir, permitindo que os usuários façam logon e se comuniquem. Talvez haja funcionalidade reduzida para usuários, dependendo de quais sistemas falharam com o servidor primário.

Na lista, selecione o pool de Front-Ends ou servidor Standard Edition que agirá como o servidor de backup para o pool. Também é possível selecionar para habilitar os intervalos de tempo de Failover e Fallback. A habilitação das configurações de tempo de failover e de fallback (especificado em segundos) permite a detecção automática de um servidor com falha, e um tempo de fallback para permitir a determinação automática de que ocorreu o backup do primário.

> [!IMPORTANT]
> Ao definir a detecção de Falha e o intervalo de Fallback, é necessário ter cuidado para não inserir um intervalo que causará o failover e fallback se o servidor não responder durante um período curto de tempo. É possível que o servidor primário não responda por curtos períodos de tempo, dependendo da carga do pool ou servidores. Os valores padrão para o failover e fallback são 300 segundos e 600 segundos de pool para pool, ou de pool para servidor Standard Edition. No caso de um Aparelho de Filial Persistente ou de um Servidor de Ramificação Persistente em um site para um pool ou servidor Standard Edition, os valores padrão são 120 segundos para failover e 240 segundos para fallback.

> [!CAUTION]
> O valor mínimo para o **intervalo de failover** não deve ser definido abaixo de 90 segundos. Se você definir o valor para menos de 90 segundos, o valor de 90 segundos será usado. O tempo de ping entre cluster é de 30 segundos, e uma configuração inferior a 90 segundos pode fazer com que os servidores primário e de backup se movimentem para cima e para baixo, causando um impacto indesejado na produção, à medida que os servidores tentam resolver o status viável do outro. Menos de 90 segundos não permitem tempo suficiente para determinar se o servidor primário está indisponível ou não.

### <a name="web-services"></a>Serviços Web

Para editar ou especificar configurações adicionais para os serviços web no pool de Front-Ends, modifique ou especifique configurações em **Serviços Web internos** e **Serviços Web externos**.

Em **Serviços Web internos**, especifique:

> [!CAUTION]
> Se você tiver mais de um pool de Front-End ou Servidor Front-End, o FQDN de serviços Web externos deve ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um Servidor Front-End como **pool01.contoso.com**, não poderá usar o **pool01.contoso.com** para outro pool de Front-End ou Servidor Front-End. Se você também estiver implantando Diretores, o FQDN de serviços Web externos definido para qualquer pool de Diretores ou Diretores deve ser exclusivo de qualquer outro diretor ou pool de Diretores, bem como de qualquer pool de Front-End ou Servidor Front-End. Se você decidir substituir os serviços Web internos por um FQDN auto-definido, cada FQDN deverá ser exclusivo de qualquer outro pool de Front-End, Diretor ou Pool de Diretores.

- Se você selecionar **Substituir FQDN**, poderá especificar um FQDN diferente para a identidade dos **Serviços Web internos** no pool. Por padrão, a configuração é o nome do pool atual, conforme definido para o pool de Front-Ends.

- Portas de escuta e de publicação para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão da porta 80 para HTTP e da porta 443 para HTTPS são as configurações mais comuns e normalmente não precisam ser alteradas, a menos que você tenha requisitos específicos dentro de sua organização e design de infraestrutura.

Em **Serviços Web externos**, especifique o seguinte:

- O FQDN dos serviços Web Externos. O FQDN especificado aqui será definido normalmente pelos requerimentos de suas exigências de conexões externas, por exemplo o proxy reverso.

- Portas de escuta e portas publicadas para HTTP e HTTPS que sua implantação exige. As definições padrão de porta 8080 para HTTP e porta 4443 para HTTPS são definidas inicialmente. Você altera as configurações para as portas de escuta com base nas exigências para seu proxy reverso e rede externa. As portas publicadas estão configuradas por padrão para a porta 80 para HTTP e porta 443 para HTTPS. Esses valores determinam que portas o pool escutará para solicitações de entrada. Normalmente, eles não precisam ser alterados, a menos que haja um conflito de requisitos de porta no pool. Espera-se portas de publicação internas e externas que usam os mesmos valores de porta. Isso não é um conflito.

### <a name="mediation-server"></a>Servidor de Mediação

Em **Servidor de Mediação**, especifique:

- Se você colocar o Servidor de Mediação com o pool, marque a caixa de seleção **Servidor de Mediação posicionado habilitado**. Se você escolher não colocar o Servidor de Mediação, nenhuma das configurações ficará disponível nesta seção.

- Se habilitar o posicionamento do Servidor de Mediação, defina o intervalo de porta de escuta nos servidores do pool para Transport Layer Security (TLS). Por padrão, essa porta é 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP (Transmission Control Protocol) para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

- Troncos associados ao Servidor de Mediação posicionado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.

- Se você tiver mais de um tronco associado a um Servidor de Mediação, poderá especificar um tronco padrão selecionando o gateway e clicando em **Tornar Padrão**. Para desmarcar um gateway como padrão, clique em **Desfazer Padrão**.

Para obter detalhes sobre como definir as configurações para o pool de Front-Ends, consulte [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).

## <a name="standard-edition-server"></a>Standard Edition Server

Você pode configurar as definições gerais, de Servidor de Mediação, serviços web e resiliência.para um servidor Standard Edition. Para maiores detalhes, leia as informações nas subseções a seguir. Para maiores detalhes sobre como definir e configurar definições para o servidor Standard Edition, consulte [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) e [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).

### <a name="general-settings"></a>Configurações Gerais

É possível definir as seguintes configurações gerais:

- **FQDN**. Observe que o FQDN não pode ser alterado. É necessário remover e redefinir o servidor Standard Edition para alterar o FQDN associado a ele.

- Selecione **Usar todos os endereços IP configurados** ou para **Limitar o uso do serviço para endereços IP selecionados**. Se você selecionar limitar o serviço para os endereços IP definidos, você definirá o endereço IP primário que o servidor usará para todas as comunicações, exceto para PSTN. Defina um endereço IP separado para uso de PSTN. Também é possível selecionar **Habilitar IPv6** para habilitar IPv6 para este servidor.

- **Habilitar porta de monitoramento do Balanceador de Carga de Hardware**. Marque a caixa de seleção e digite o número de porta que seu Balanceador de carga de hardware usará para monitorar o estado do pool.

- Em **Recursos e Funcionalidade**, defina as funções adicionais que deseja colocar com este servidor. Você pode configurar as seguintes definições:

  - **Conferência**. Inclui áudio, vídeo e compartilhamento de aplicativos. Após selecionar esta opção, você pode selecionar **Conferência discada (PSTN)**. Você pode especificar e definir um gateway PSTN mais tarde nas definições do Servidor de Mediação.

  - **Enterprise Voice**. Habilita chamadas internas de voz sobre IP a dispositivos e dispositivos qualificados e Skype for Business clientes. Para habilitar os recursos de chamada externa, é necessário incluir um Servidor de Mediação. Para obter detalhes, consulte "Servidor de Mediação" posteriormente neste tópico.

- Em **Associações**, é possível editar o seguinte:

  - Selecione **Repositório do SQL Server** para associar um repositório do SQL a um servidor Front-End. Também é possível habilitar o espelhamento e selecionar um servidor de testemunha de espelhamento.

  - **Compartilhamento de arquivo**. Modifique o repositório de arquivo usado pelo servidor Standard Edition. É possível selecionar um novo repositório de arquivo entre aqueles já definidos, selecionando-o na lista. É possível criar um novo repositório de arquivo clicando em **Novo**.

    > [!IMPORTANT]
    > Antes de publicar a topologia recém-definida, o servidor especificado precisa existir e fazer parte do domínio.

  - **Arquivamento**. Associe um repositório do SQL Server de Arquivamento ao servidor Standard Edition. É possível selecionar um repositório de Arquivamento já definido selecionando o servidor na lista, ou clique em **Novo** para especificar um novo repositório de Arquivamento.

    > [!IMPORTANT]
    > Antes de publicar a topologia recém-definida, o servidor especificado precisa existir e fazer parte do domínio.

  - **Monitoramento (métricas de CDR e QoE)**. Associe um repositório do SQL Server de Monitoramento ao servidor Standard Edition. É possível selecionar um Servidor de Monitoramento já definido, selecionando-o na lista,, ou clicar em **Novo** para especificar um novo Servidor de Monitoramento.

  - **Associar pool a um Office Web Apps Server**. Selecione essa opção para associar um Office Web Apps Server ao pool de Front-Ends. Selecione um servidor existente na lista, ou clique em **Novo** para criar um novo Office Web Apps Server.

  - **Associar pool de Borda**. Associe um Servidor de Borda ou pool ao servidor Standard Edition. É possível selecionar um Servidor de Borda ou pool já definido selecionando o servidor na lista, ou clique em **Novo** para especificar um novo Servidor de Borda ou pool.

### <a name="resiliency"></a>Resiliência

Resiliência fornece recuperação de desastre e alta disponibilidade para o servidor. Ao fornecer um backup, se o servidor primário falhar, o backup poderá assumir, permitindo que os usuários façam logon e se comuniquem. É possível que ocorra uma redução de funcionalidade para os usuários, dependendo de quais sistemas falharam.

Na lista, selecione o pool de Front-Ends ou servidor Standard Edition que agirá como o backup para o servidor. Também é possível selecionar para habilitar os intervalos de tempo de Failover e Fallback. A habilitação das configurações de tempo de failover e de fallback (especificado em segundos) permite a detecção automática de um Registrador com falha, e um tempo de fallback para permitir a determinação automática de que ocorreu o backup do primário.

> [!IMPORTANT]
> Ao definir a detecção de Falha e o intervalo de Fallback, é necessário ter cuidado para não inserir um intervalo que causará o failover e fallback se o servidor não responder durante um período curto de tempo. É possível que o servidor primário não responda por curtos períodos de tempo, dependendo da carga do pool ou servidores. Os valores padrão para o failover e fallback são 300 segundos e 600 segundos de pool para pool, ou de pool para servidor Standard Edition. No caso de um Aparelho de Filial Persistente ou de um Servidor de Ramificação Persistente em um site para um pool ou servidor Standard Edition, os valores padrão são 120 segundos para failover e 240 segundos para fallback.

### <a name="web-services"></a>Serviços Web

Para editar ou especificar definições adicionais no servidor, modifique ou especifique definições em **serviços Web Internos** e **serviços Web Externos**.

Para **serviços Web Internos**, você pode especificar:

- Se você selecionou Substituir FQDN, poderá especificar um FQDN diferente para a identidade dos Serviços Web internos no servidor. Por padrão, a configuração é o nome do servidor atual, conforme definido para o servidor Standard Edition.

- Portas de escuta e de publicação para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão da porta 80 para HTTP e da porta 443 para HTTPS são as configurações mais comuns e normalmente não precisam ser alteradas, a menos que você tenha requisitos específicos dentro de sua organização e design de infraestrutura.

Para **Serviços Web externos**, é possível especificar o seguinte:

- O FQDN dos serviços Web Externos. O FQDN especificado aqui será normalmente definido pelas exigências de suas necessidades de conexão externa, como o proxy reverso.

- Portas de escuta para HTTP e HTTPS que sua implantação exige. As definições padrão de porta 8080 para HTTP e porta 4443 para HTTPS são definidas inicialmente. Você altera as configurações para as portas de escuta com base nas exigências para seu proxy reverso e rede externa. Esses valores determinam que portas o pool escutará para solicitações de entrada. Normalmente não precisam ser alteradas, a não ser que haja um conflito de exigências de porta no pool.

### <a name="mediation-server"></a>Servidor de Mediação

Para o  **Servidor de Mediação**, você pode especificar:

- Se você colocar o Servidor de Mediação com o servidor, marque a caixa de seleção **Servidor de Mediação posicionado habilitado**. Se você escolher não colocar o Servidor de Mediação, nenhuma das configurações ficará disponível nesta seção.

- Se você tiver habilitado o posicionamento do Servidor de Mediação, defina o intervalo de porta de escuta no servidor para TLS. Por padrão, essa porta é 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional e você deve consultar os requisitos de seu gateway ou os requisitos de sua PSTN a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

- Troncos associados ao Servidor de Mediação posicionado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.

- Se você tiver mais de um gateway associado a um Servidor de Mediação, poderá especificar um gateway padrão selecionando o gateway e clicando em **Tornar Padrão**. Para desmarcar um gateway como padrão, clique em **Desfazer Padrão**.

Para obter detalhes sobre como definir as configurações para o servidor Standard Edition, consulte [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) e [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).