---
title: Expansor de configurações gerais de Front End do Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Você pode editar as propriedades do pool do servidor Front-End ou Front-End editando ou configurar os seguintes atributos. A página de configuração é separada nas seguintes seções:'
ms.openlocfilehash: 4d18d8499c053d2fbed5b0b3dba97bda263f28cd
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504086"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de configurações gerais de Front End do Lync Server 2010
 
Você pode editar as propriedades do pool do servidor Front-End ou Front-End editando ou configurar os seguintes atributos. A página de configuração é separada nas seguintes seções:
  
 **Geral**
  
- **FQDN**: O nome de domínio totalmente qualificado do pool de Front-End ou de servidor Front-End.
    
- Selecione **usar todos os endereços IP configurados** para fazer uso de todos os endereços configurados no pool de Front-End ou de servidor Front-End.
    
    > [!IMPORTANT]
    > Você não deve selecionar essa opção se você colocar o servidor de mediação no pool de Front-End ou servidor Front-End. Servidores de mediação e servidores Front-End precisam endereços IP dedicados no qual você deseja se comunicar. 
  
- Selecione **limitar o uso do serviço aos endereços IP selecionados** e insira o endereço IP para o **endereço IP principal** para a comunicação de pool de Front-End ou de servidor Front-End com o restante da implantação. Em **endereço IP PSTN** , digite o endereço IP associado com o servidor de mediação.
    
    **Recursos e funcionalidades**
    
- **Conferência**: marque a caixa de seleção se quiser que os recursos de conferência em sua implantação. As conferências incluem áudio, vídeo, compartilhamento de aplicativos, compartilhamento de desktop e webconferência. Você precisará criar e associar um Office Web Apps Server para Webconferência (definida mais adiante nesta página de propriedades).
    
- Se você selecionou a conferência, **conferência discada (PSTN)** podem ser selecionadas. Marque a caixa de seleção para habilitar os recursos de conferência discada.
    
- Marque a caixa de seleção **Enterprise Voice** , se você pretende implantar recursos para habilitar o Lync Server 2013 agir como seu sistema de voz do telefone usando a voz sobre tecnologias IP (VoIP), incluindo a opção de implantar telefones do fone, SIP trunks ou público conectividade de rede telefônica comutada usando o servidor de mediação, Gateways PSTN e PBX IP, em combinação ou sozinhos, com base no design e requisitos. Para detalhes sobre o Enterprise Voice, consulte [Enterprise Voice](http://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) e [Planejar o Enterprise Voice no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)
    
    **Associações**
    
- **O SQL Server store**: O FQDN do SQL Server (e, opcionalmente, uma instância nomeada) associado ao pool de Front-End ou de servidor Front-End. Selecione o repositório do SQL Server a lista ou criar um novo repositório do SQL Server, clicando em **novo**
    
- **Repositório de arquivo**: você selecione o FQDN do servidor e o compartilhamento (no formato `\\<FQDN of server>\<share name>`) que atuará como o local do repositório de arquivo para os arquivos compartilhados que Lync Server 2013 cria e usa para replicação, diretórios de conferência e outros fins. Selecione o repositório de arquivos a lista ou criar um novo repositório de arquivos, clicando em **novo**.
    
- Marque a caixa de seleção **Associar servidor de arquivamento** para habilitar um servidor de arquivamento para este pool de Front-End ou de servidor Front-End. Depois de selecionar a caixa de seleção, você selecionar um servidor de arquivamento existentes da lista ou clique em **novo** para criar as definições para um novo servidor de arquivamento.
    
- Marque a caixa de seleção **Associar Monitoring Server** para habilitar um Monitoring Server para este pool de Front-End ou de servidor Front-End. Depois de selecionar a caixa de seleção, que você selecione um Monitoring Server existente na lista ou clique em **novo** para criar as definições para um novo Monitoring Server.
    
- Selecione o **associar Pool de borda (para componentes de mídia** caixa de seleção para habilitar um servidor de borda para este pool de Front-End ou de servidor Front-End. Depois de selecionar a caixa de seleção, que você selecione um pool ou servidor de borda existente na lista ou clique em **novo** para criar as definições para um novo servidor de borda ou pool.
    
 **Resiliência**
  
- Marque a caixa de seleção de **pool registrador de backup associado** para selecione na lista um pool de Front-End ou de servidor Front-End que será o registrador de backup (ou seja, o servidor Front-End ou Front End pool designado como um registrador secundário em caso onde o principal Falha)
    
- Se você selecionou o pool registrador de backup associado e tiver escolhido um registrador de backup, você pode selecionar a caixa de seleção para **failover automático e failback para voz**. Agora você pode definir propriedades numéricas para **voz failover detecção interna (s)** e **o intervalo de failback de voz (s)**. Para obter detalhes, consulte [Planning for Enterprise Voice Resiliency](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
    
 **Serviços da Web**
  
- Para configurar **serviços web internos**, você pode definir **as portas de escuta** para **HTTP** e **HTTPS**. Por padrão, essas são a porta 80 do TCP e porta TCP 443, respectivamente. Você também pode configurar as **portas publicados** para **HTTP** e **HTTPS**. Por padrão, essas são a porta 80 do TCP e porta TCP 443, respectivamente. Com base em sua configuração de serviços web internos e uso dos balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga DNS), ajustar os valores de porta para definir a escuta e portas publicadas.
    
    > [!IMPORTANT]
    > Serviços web internos e definidos de escuta e portas publicadas são para dispositivos e clientes internos. Dispositivos e clientes externos usam os serviços web externos de escuta e publicadas portas, juntamente com o nome de domínio totalmente qualificado de serviços web externos definido (FQDN). 
  
- Para configurar os **serviços web externos**, você pode definir **as portas de escuta** para **HTTP** e **HTTPS**. Por padrão, essas são a porta 80 do TCP e porta TCP 443, respectivamente. Você também pode configurar as **portas publicados** para **HTTP** e **HTTPS**. Por padrão, essas são a porta 80 do TCP e porta TCP 443, respectivamente. Com base em sua configuração de serviços web internos e uso dos balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga DNS), ajustar os valores de porta para definir a escuta e portas publicadas.
    
    > [!IMPORTANT]
    > Serviços web externos e escutando definido e portas publicadas são para dispositivos e clientes externos. Dispositivos e clientes externos usam os serviços web externos de escuta e publicadas portas, geralmente é definidas por seu proxy reverso, juntamente com o nome de domínio totalmente qualificado de serviços web externos definido (FQDN). A relação entre o FQDN de serviços web externos e os URLs simples definem os endereços de uniform resource locator (URL) clientes externos usarão para acessar os serviços disponíveis para usuários externos e dispositivos. Para obter mais detalhes sobre URLs simples, consulte [Planning for Simple URLs](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx). 
  
 **Servidor de Mediação**
  
- Para configurar as propriedades do **Servidor de mediação** para um servidor de mediação colocado (ou seja, um servidor de mediação implantados no pool de Front-End ou de servidor Front-End), selecione o **servidor de mediação posicionado habilitado**.
    
- Para definir as **portas de escuta** para um servidor de mediação colocado, você deve digitar o valor **TLS** e **TCP** da porta que o servidor de mediação colocado está ouvindo. Por padrão, o TLS é definido como a porta TCP 5067.
    
- Para definir um valor de porta TCP para o servidor de mediação, você deve selecionar a caixa de seleção **Habilitar TCP porta** . Por padrão, o servidor de mediação usa a segurança de camada de transporte (TLS) sobre o protocolo TCP. Portas TCP estão disponíveis somente quando a seleção de habilitar a porta TCP está habilitada.
    
    > [!NOTE]
    > Esta é uma configuração opcional e você deve referir-se aos requisitos da PSTN ou gateway para determinar se é necessário que isso. Por padrão, o valor da porta TCP é 5068. 
  
- Você definir troncos que estão associados com o servidor de mediação colocado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.
    
    Se você tiver mais de um gateway associado a um servidor de mediação, você pode especificar o gateway padrão selecionando o gateway que você deseja tornar o padrão e, em seguida, clicando em **Tornar padrão**. Se você optar por remover o gateway padrão atual, selecione o gateway e clique em **Unmake padrão**.
    
> [!IMPORTANT]
> Se você fizer alterações para as propriedades nessa caixa de diálogo, você deve publicar a topologia e executar o Skype para o Assistente de implantação de servidor de negócios em todos os servidores afetados. Após publicar a nova topologia, uma lista dos servidores afetados onde o Skype para o Assistente de implantação do Business Server deve ser executado é fornecida a você como um link na tela se resumo publishing topologia bem-sucedida. Para obter detalhes sobre a topologia atualizada de publicação, consulte [Publish the Topology](http://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Para obter detalhes sobre o Skype para o Assistente de implantação do Business Server, consulte [Lync Server Administrative Tools](http://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx). 
  
Clique em **Okey** para salvar e confirmar suas alterações no documento de topologia.
  
Clique em **Cancelar** para descartar suas alterações e fechar as **Editar propriedades** para o pool de Front-End ou de servidor Front-End.
  
Clique em **Ajuda** para ler esse tópico de Ajuda.
  
## <a name="see-also"></a>Consulte também

[Definir e configurar um Pool de Front-End ou servidor Standard Edition](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)