---
title: Expansor de Configurações Gerais de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Para editar as configurações de um pool de Front-Ends ou servidor Standard Edition existente, as seguintes seções são disponibilizadas:'
ms.openlocfilehash: 6ec94dffe46bf29b7665ef362f8084a8fd2a4948
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988908"
---
# <a name="front-end-general-settings-expander"></a>Expansor de Configurações Gerais de Front-End
 
Para editar as configurações de um pool de Front-Ends ou servidor Standard Edition existente, as seguintes seções são disponibilizadas:
  
- Configurações gerais
    
- Configurações de resiliência
    
- Configurações de serviços Web
    
- Configurações do Servidor de Mediação
    
## <a name="front-end-pool"></a>Pool de Front-Ends

Para um pool de Front-Ends, é possível definir configurações gerais, de resiliência, serviços Web e Servidor de Mediação. Para obter detalhes, consulte as informações nas subseções a seguir. Para obter detalhes sobre como definir e configurar as definições para o pool de Front-End, consulte [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).
  
### <a name="general-settings"></a>Configurações gerais

Você pode definir as seguintes configurações gerais:
  
- **FQDN**. Edite o FQDN do pool para alterá-lo.
    
- **Habilitar porta de monitoramento do balanceador de carga de hardware**. Marque a caixa de seleção e digite o número da porta que seu balanceador de carga de hardware usará para monitorar o estado dos servidores do pool.
    
- Em **Recursos e Funcionalidade**, defina as outras funções que você deseja colocar com esse pool. As seguintes configurações podem ser definidas:
    
  - **Conferência**. Inclui compartilhamento de áudio, vídeo e aplicativos. Após a seleção dessa opção, a conferência Discada (PSTN) poderá ser selecionada. Você especificará e definirá um gateway PSTN (rede telefônica pública comutada) na subseção "Configurações do Servidor de Mediação" mais adiante nesta seção.
    
  - **Enterprise Voice**. Habilita o voice interna chamadas IP qualificados aparelhos de telefone e dispositivos e Skype para clientes corporativos. Para habilitar os recursos de chamada externa, é necessário incluir um Servidor de Mediação. Para obter detalhes, consulte "Servidor de Mediação" mais adiante neste tópico.
    
- Em **Associações**, edite ou especifique o seguinte:
    
  - **Repositório SQL**. Modifique um banco de dados SQL Server existente ou crie um novo banco de dados baseado no SQL Server para armazenar os bancos de dados do pool de Front-Ends. Você pode selecionar uma nova instância do SQL Server na lista ou criar uma nova entrada clicando em **Novo**.
    
    Selecione **Habilitar espelhamento do repositório do SQL Server** e, em seguida, selecione o servidor a ser usado para espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.
    
    Selecione **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar o servidor a ser usado como testemunha de espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.
    
  - **Compartilhamento de arquivo**. Modifique o repositório de arquivos usado pelo pool de Front-Ends. Você pode selecionar um novo repositório de arquivos entre os já definidos, selecionando-o na lista. Também pode criar um novo repositório clicando em **Novo**.
    
    > [!IMPORTANT]
    > Antes da publicação da topologia recém-definida, o servidor especificado precisa existir e ter ingressado no domínio. 
  
  - **Arquivamento**. Associe um repositório de Servidor de Arquivamento ao pool de Front-Ends. Você pode selecionar um repositório do SQL Server de Arquivamento já definido escolhendo o servidor na lista ou clicar em **Novo** para especificar um novo Servidor de Arquivamento.
    
    > [!IMPORTANT]
    > Antes da publicação da topologia recém-definida, o servidor especificado precisa existir e ter ingressado no domínio. 
  
    Selecione **Habilitar espelhamento de repositório do SQL Server** e, em seguida, selecione o servidor a ser usado para espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.
    
    Selecione **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar o servidor a ser usado como testemunha de espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.
    
  - **Monitoramento (métricas de CDR e QoE)**. Selecione esta opção para associar um repositório do SQL Server de Monitoramento ao pool de Front-Ends. Você pode selecionar um Servidor de Monitoramento já definido escolhendo-o na lista ou clicar em **Novo** para especificar um novo Servidor de Monitoramento.
    
    Selecione **Habilitar espelhamento do repositório do SQL Server** e, em seguida, selecione o servidor a ser usado para espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.
    
    Selecione **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar o servidor a ser usado como testemunha de espelhamento. Clique em **Novo** para criar um novo repositório do SQL Server.
    
  - **Associar pool de Borda (para componentes de mídia)**. Associe um Servidor de Borda ou pool ao pool de Front-Ends. Você pode selecionar um Servidor de Borda ou pool já definido escolhendo o servidor na lista ou clicar em **Novo** para especificar um novo Servidor de Borda ou pool.
    
  - **Associar pool a um Servidor do Office Web Apps**. Selecione esta opção para associar um Servidor do Office Web Apps ao pool de Front-Ends. Selecione um servidor existente na lista ou clique em **Novo** para criar um novo Servidor do Office Web Apps.
    
### <a name="resiliency"></a>Resiliência

A resiliência fornece recuperação de desastre e alta disponibilidade para o pool. Ao fornecer um backup, se o servidor primário falhar, o servidor de backup poderá assumir o controle, permitindo que os usuários se conectem e se comuniquem. Talvez haja funcionalidade reduzida para os usuários, dependendo de quais sistemas falharam com o servidor primário.
  
Na lista, selecione o pool de Front-Ends ou servidor Standard Edition que funcionará como o servidor de backup do pool. Também é possível selecionar a opção para habilitar os intervalos de tempo de Failover e Fallback. A habilitação das configurações de tempo de failover e de fallback (especificadas em segundos) permite a detecção automática de um servidor com falha, bem como um tempo de fallback para permitir a determinação automática de que ocorreu o backup do servidor primário.
  
> [!IMPORTANT]
> Ao definir a detecção de Falha e o intervalo de Fallback, é necessário ter cuidado para não inserir um intervalo que causará o failover e o fallback se o servidor não responder durante um período curto de tempo. É possível que o servidor primário não responda por curtos períodos de tempo, dependendo da carga do pool ou dos servidores. Os valores padrão para o failover e o fallback são 300 segundos e 600 segundos de pool para pool ou do pool para o servidor Standard Edition. No caso de um Aparelho de Filial Persistente ou de um Servidor de Filial Persistente em um site para um pool ou um servidor Standard Edition, os valores padrão são 120 segundos para failover e 240 segundos para fallback. 
  
> [!CAUTION]
> O valor mínimo do **intervalo de failover** não deve ser definido abaixo de 90 segundos. Se você definir um valor inferior, o valor de 90 segundos será usado. O tempo de ping entre clusters é de 30 segundos, e uma configuração inferior a 90 segundos poderá resultar no funcionamento instável dos servidores primário e de backup, causando um impacto indesejado na produção, à medida que os servidores tentam resolver o status viável do outro. Com um valor inferior a 90 segundos, não há tempo suficiente para determinar se o servidor primário não está disponível realmente.
  
### <a name="web-services"></a>Serviços Web

Para editar ou especificar configurações adicionais para os serviços Web no pool de Front-Ends, modifique ou especifique as configurações em **Serviços Web internos** e **Serviços Web externos**.
  
Em **Serviços Web internos**, especifique o seguinte:
  
> [!CAUTION]
> Se você tiver mais de um pool de Front-End ou servidor Front-End, os serviços Web externos FQDN deve ser exclusivo. Por exemplo, se você definir os serviços Web externos FQDN de um servidor Front-End como **pool01. contoso.com**, você não pode usar **pool01. contoso.com** para outro pool de Front-End ou servidor Front-End. Se você estiver implantando também diretores, o FQDN de serviços Web externos definidas para qualquer Diretor ou pool de diretores deve ser exclusivo de qualquer outro diretor ou diretor pool, conforme, bem como qualquer Front-End do pool ou servidor Front-End. Se você decidir substituir os serviços web internos com um FQDN auto-definido, cada FQDN deve ser exclusivo de qualquer outro pool Front-End, diretor ou diretor pool.
  
- Se você selecionar **Substituir FQDN**, poderá especificar um FQDN diferente para a identidade dos serviços **Web internos** no pool. Por padrão, a configuração é o nome do pool atual, conforme definido para o pool de Front-Ends.
    
- Portas de escuta e publicadas para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão de porta 80 para HTTP e de porta 443 para HTTPS são as mais comuns e normalmente não precisam ser alteradas, a menos que sua organização e o design de sua infraestrutura tenham requisitos específicos.
    
Em **Serviços Web externos**, especifique o seguinte:
  
- O FQDN dos Serviços Web externos. O FQDN especificado aqui será normalmente definido pelos seus requisitos de conexão externa, como o proxy reverso.
    
- Portas de escuta e publicadas para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão da porta 8080 para HTTP e a porta 4443 para HTTPS são definidas inicialmente. Você poderá alterar essas configurações para as portas de escuta com base nos requisitos de proxy reverso e de rede externa. As portas publicadas estão definidas como padrão da porta 80 para HTTP e a porta 443 para HTTPS. Esses valores determinam quais portas o pool escutará para solicitações de entrada. Geralmente, essas não precisará ser alterado, a menos que haja um conflito de requisitos de porta no pool. Espera-se portas publicadas internas e externas usando os mesmos valores de porta. Isso não é um conflito.
    
### <a name="mediation-server"></a>Servidor de Mediação

Em **Servidor de Mediação**, especifique o seguinte:
  
- Se você colocar o Servidor de Mediação com o pool, marque a caixa de seleção **Servidor de Mediação posicionado habilitado**. Se você optar por não colocar o Servidor de Mediação, nenhuma das configurações estará disponível nesta seção.
    
- Se você habilitar a colocação do Servidor de Mediação, defina o intervalo de porta de escuta nos servidores do pool para TLS. Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deverá verificar seus requisitos de gateway ou PSTN a fim de determinar se isso é necessário. Por padrão, o valor da porta TCP é 5068.
    
- Troncos associados ao Servidor de Mediação colocado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação. 
    
- Se houver mais de um tronco associado a um Servidor de Mediação, você poderá especificar um tronco padrão selecionando o gateway e clicando em **Tornar Padrão**. Para cancelar a seleção de um gateway como o padrão, clique em **Desfazer Padrão**. 
    
Para obter detalhes sobre como definir e configurar as definições para o pool de Front-End, consulte [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).
  
## <a name="standard-edition-server"></a>Servidor Standard Edition

Para um servidor Standard Edition, você pode definir configurações gerais, de resiliência, serviços Web e Servidor de Mediação. Para obter detalhes, consulte as informações nas subseções a seguir. Para obter detalhes sobre como definir e configurar as definições para o servidor Standard Edition, consulte [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).
  
### <a name="general-settings"></a>Configurações gerais

Você pode definir as seguintes configurações gerais:
  
- **FQDN**. Observe que o FQDN não pode ser alterado. É necessário remover e redefinir o servidor Standard Edition para alterar o FQDN associado a ele.
    
- Selecione **Usar todos os endereços IP configurados** ou **Limitar o uso do serviço para os endereços IP selecionados**. Caso selecione a opção para limitar o serviço aos endereços IP definidos, você definirá o endereço IP primário que o servidor usará para todas as comunicações, exceto para PSTN. Defina um endereço IP diferente para uso da PSTN. Você também pode selecionar **Habilitar IPv6** a fim de habilitar o IPv6 para esse servidor.
    
- **Habilitar porta de monitoramento do balanceador de carga de hardware**. Marque a caixa de seleção e insira o número de porta que seu balanceador de carga de hardware usará para monitorar o estado do servidor.
    
- Em **Recursos e Funcionalidade**, defina as outras funções que você deseja colocar com esse servidor. As seguintes configurações podem ser definidas:
    
  - **Conferência**. Inclui compartilhamento de áudio, vídeo e aplicativos. Após a seleção dessa opção, selecione **Conferência discada (PSTN)**. Você poderá especificar e definir um gateway PSTN mais adiante em configurações do Servidor de Mediação.
    
  - **Enterprise Voice**. Habilita o voice interna chamadas IP qualificados aparelhos de telefone e dispositivos e Skype para clientes corporativos. Para habilitar os recursos de chamada externa, é necessário incluir um Servidor de Mediação. Para obter detalhes, consulte "Servidor de Mediação" mais adiante neste tópico.
    
- Em **Associações**, você pode editar ou especificar o seguinte:
    
  - Selecione **Repositório do SQL Server** para associar um repositório do SQL Server ao servidor Front-End. Você também pode habilitar o espelhamento e selecionar um servidor de testemunha de espelhamento.
    
  - **Compartilhamento de arquivo**. Modifique o repositório de arquivos usado pelo servidor Standard Edition. Você pode selecionar um novo repositório de arquivos entre os já definidos, escolhendo-o na lista. Também pode criar um novo repositório clicando em **Novo**.
    
    > [!IMPORTANT]
    > Antes da publicação da topologia recém-definida, o servidor especificado precisa existir e ter ingressado no domínio. 
  
  - **Arquivamento**. Associe um repositório de Servidor de Arquivamento ao servidor Standard Edition. Você pode selecionar um repositório de Arquivamento já definido escolhendo o servidor na lista ou clicar em **Novo** para especificar um novo repositório de Arquivamento.
    
    > [!IMPORTANT]
    > Antes da publicação da topologia recém-definida, o servidor especificado precisa existir e ter ingressado no domínio. 
  
  - **Monitoramento (métricas de CDR e QoE)**. Associe um repositório do SQL Server de Monitoramento ao servidor Standard Edition. Você pode selecionar um Servidor de Monitoramento já definido escolhendo-o na lista, ou clicar em **Novo** para especificar um novo Servidor de Monitoramento.
    
  - **Associar pool a um Servidor do Office Web Apps**. Selecione esta opção para associar um Servidor do Office Web Apps ao pool de Front-Ends. Selecione um servidor existente na lista ou clique em **Novo** para criar um novo Servidor do Office Web Apps.
    
  - **Associar pool de Borda**. Associe um Servidor de Borda ou pool ao servidor Standard Edition. Você pode selecionar um Servidor de Borda ou pool já definido escolhendo o servidor na lista ou clicar em **Novo** para especificar um novo Servidor de Borda ou pool.
    
### <a name="resiliency"></a>Resiliência

A resiliência fornece recuperação de desastre e alta disponibilidade para o pool. Ao fornecer um backup, se o servidor primário falhar, o servidor de backup poderá assumir o controle, permitindo que os usuários façam logon e se comuniquem. Talvez haja funcionalidade reduzida para os usuários, dependendo de quais sistemas também falharam.
  
Na lista, selecione o pool de Front-Ends ou servidor Standard Edition que funcionará como o backup do servidor. Também é possível selecionar a opção para habilitar os intervalos de tempo de Failover e Fallback. A habilitação das configurações de tempo de failover e de fallback (especificadas em segundos) permite a detecção automática de um Registrador Avançado com falha, bem como um tempo de fallback para permitir a determinação automática de que ocorreu o backup do servidor primário.
  
> [!IMPORTANT]
> Ao definir a detecção de Falha e o intervalo de Fallback, é necessário ter cuidado para não inserir um intervalo que causará o failover e o fallback se o servidor não responder durante um período curto de tempo. É possível que o servidor primário não responda por curtos períodos de tempo, dependendo da carga do pool ou dos servidores. Os valores padrão para o failover e o fallback são 300 segundos e 600 segundos de pool para pool ou do pool para o servidor Standard Edition. No caso de um Aparelho de Filial Persistente ou de um Servidor de Filial Persistente em um site para um pool ou um servidor Standard Edition, os valores padrão são 120 segundos para failover e 240 segundos para fallback. 
  
### <a name="web-services"></a>Serviços Web

Para editar ou especificar configurações adicionais para os serviços Web no servidor, modifique ou especifique as configurações em **Serviços Web internos** e **Serviços Web externos**.
  
Em **Serviços Web internos**, especifique o seguinte:
  
- Se você selecionar Substituir FQDN, poderá especificar um FQDN diferente para a identidade dos serviços Web internos no servidor. Por padrão, a configuração é o nome do servidor atual, conforme definido para o servidor Standard Edition.
    
- Portas de escuta e publicadas para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão de porta 80 para HTTP e de porta 443 para HTTPS são as mais comuns e normalmente não precisam ser alteradas, a menos que sua organização e o design de sua infraestrutura tenham requisitos específicos.
    
Em **Serviços Web externos**, especifique o seguinte:
  
- O FQDN dos Serviços Web externos. O FQDN especificado aqui será normalmente definido pelos seus requisitos de conexão externa, como o proxy reverso.
    
- Portas de escuta para HTTP e HTTPS exigidas pela sua implantação. A configuração padrão da porta 8080 para HTTP e da porta 4443 para HTTPS é definida inicialmente. Você poderá alterar essas configurações para as portas de escuta com base nos requisitos de proxy reverso e de rede externa. Esses valores determinam quais portas o servidor escutará aguardando solicitações de entrada. Normalmente, não é necessário alterá-los, a menos que haja conflito de requisitos de porta no servidor. 
    
### <a name="mediation-server"></a>Servidor de Mediação

Em **Servidor de Mediação**, você pode especificar o seguinte:
  
- Se você colocar o Servidor de Mediação com o servidor, marque a caixa de seleção **Servidor de Mediação posicionado habilitado**. Se você optar por não colocar o Servidor de Mediação, nenhuma das configurações estará disponível nesta nesta seção. 
    
- Se você tiver habilitado a colocação do Servidor de Mediação, defina o intervalo de porta de escuta no servidor para TLS. Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deverá verificar seus requisitos de gateway ou PSTN a fim de determinar se isso é necessário. Por padrão, o valor da porta TCP é 5068.
    
- Troncos associados ao Servidor de Mediação colocado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação. 
    
- Se houver mais de um tronco associado a um Servidor de Mediação, você poderá especificar um tronco padrão selecionando o gateway e clicando em **Tornar Padrão**. Para cancelar a seleção de um gateway como padrão, clique em **Desfazer Padrão**. 
    
Para obter detalhes sobre como definir e configurar as definições para o servidor Standard Edition, consulte [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).
  

