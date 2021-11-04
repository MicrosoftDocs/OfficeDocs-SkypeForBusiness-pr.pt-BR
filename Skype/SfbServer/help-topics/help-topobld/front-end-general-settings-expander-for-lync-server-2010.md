---
title: Expansor de Configurações Gerais de Front End para Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Edite as propriedades do Servidor front-end ou pool de front-end editando ou configurando os atributos a seguir. A página de configuração é separada nas seguintes seções:'
ms.openlocfilehash: d7257a8abf61f2d081562e72b40811017dcefaa0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768769"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de Configurações Gerais de Front-end para Lync Server 2010

Edite as propriedades do Servidor front-end ou pool de front-end editando ou configurando os atributos a seguir. A página de configuração é separada nas seguintes seções:

 **Geral**

- **FQDN**: o nome de domínio totalmente qualificado do Servidor front-end ou pool de front-end.

- Selecione **Usar todos os endereços IP configurados** para usar todos os endereços configurados no Servidor Front-End ou no pool de Front-End.

    > [!IMPORTANT]
    > Você não deve selecionar essa opção se você colocar o Servidor de Mediação no Servidor de Front-End ou pool de Front-End. Servidores de Mediação e Servidores Front-End precisam de endereços IP dedicados nos quais se comunicar.

- Selecione **Limitar o uso do serviço** para endereços IP selecionados e insira o endereço IP do endereço **IP** principal para a comunicação do servidor front-end ou do pool de front-end com o restante da implantação. Digite no **endereço IP PSTN** o endereço IP associado ao Servidor de Mediação.

    **Recursos e funcionalidade**

- **Conferência**: marque a caixa de seleção se você quiser recursos de conferência em sua implantação. A conferência inclui áudio, vídeo, compartilhamento de aplicativo, compartilhamento de desktop e conferência da Web. Você precisará criar e associar um servidor Office Web Apps para Webconferência (definido posteriormente nesta página Propriedades).

- Se você selecionou Conferência, será possível selecionar **Conferência discada (PSTN)**. Marque a caixa de seleção para habilitar os recursos de conferência discada.

- Marque a caixa de seleção Enterprise Voice se você pretende implantar recursos para habilitar o Lync Server 2013 a atuar como seu sistema de voz telefônica usando tecnologias voIP (voz sobre IP), incluindo **a** opção de implantar telefones de handset, troncos SIP ou conectividade de rede telefônica pública comutado usando o Servidor de Mediação, Gateways PSTN e IP-PBX, em combinação ou sozinha,  com base no design e nos requisitos. Para detalhes sobre Enterprise Voice, consulte [Enterprise Voice](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice) [e Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associações**

- **SQL Server :** O FQDN do SQL Server (e, opcionalmente, uma instância nomeada) associado ao Servidor de Front-End ou pool de Front-End. Selecione o SQL Server store na lista ou crie um novo SQL Server store clicando em **Novo**

- **Armazenamento de** arquivos : você seleciona o FQDN do servidor e o compartilhamento (no formato ) que atuará como o local do armazenamento de arquivos para os arquivos compartilhados que o Lync Server 2013 cria e usa para replicação, diretórios de conferência e outras  `\\<FQDN of server>\<share name>` finalidades. Selecione o Repositório de arquivo na lista ou crie um novo Repositório de arquivo clicando em **Novo**

- Marque a **caixa de seleção** Associar Servidor de Arquivamento para habilitar um Servidor de Arquivamento para esse servidor front-end ou pool de front-end. Depois de selecionar a caixa de seleção, selecione um Servidor de Arquivamento existente na lista ou clique em **Novo** para criar as definições de um novo Servidor de Arquivamento.

- Marque a caixa de seleção Associar **Servidor de Monitoramento** para habilitar um Servidor de Monitoramento para esse servidor front-end ou pool de front-end. Depois de selecionar a caixa de seleção, selecione um Servidor de Monitoramento existente na lista ou clique em **Novo** para criar as definições de um novo Servidor de Monitoramento.

- Selecione a caixa de seleção Associar Pool de **Borda (para** componentes de mídia para habilitar um Servidor de Borda para esse Servidor front-end ou pool de front-end. Depois de selecionar a caixa de seleção, selecione um Servidor de Borda ou pool existente na lista ou clique em **Novo** para criar as definições para um novo Servidor de Borda ou pool.

  **Resiliência**

- Marque a caixa de seleção Pool de **Registradores** de backup associado para selecionar na lista um Servidor front-end ou pool de front-end que será o Registrador de backup ( ou seja, o Servidor front-end ou pool de front-end designado como um registrador secundário no caso de falha principal)

- Se você selecionou Pool associado de Registradores de backup e escolheu um registrador de backup, poderá marcar a caixa de seleção para **Failover e failback automático para Voz**. Agora é possível definir as propriedades numéricas para **Detecção interna de failover de voz (seg.)** e **Intervalo de failback de voz (seg.)**. Para obter detalhes, consulte [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)

  **Serviços Web**

- Para configurar os **Serviços internos da Web**, defina as **Portas de escuta** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Configure também as **Portas publicadas** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Com base em sua configuração de serviços Web internos e uso dos balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga DNS), ajuste os valores de porta para definir as portas de escuta e de publicação.

    > [!IMPORTANT]
    > Os serviços internos da Web e as portas definidas de escuta e publicação servem para clientes e dispositivos internos. Clientes e dispositivos externos usam as portas de escuta e publicação de serviços Web externos, junto com o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos definidos.

- Para configurar os **Serviços Externos da Web**, defina as **Portas de escuta** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Configure também as **Portas publicadas** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Com base em sua configuração de serviços Web internos e uso dos balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga DNS), ajuste os valores de porta para definir as portas de escuta e de publicação.

    > [!IMPORTANT]
    > Os serviços externos da Web e as portas definidas de escuta e publicação servem para clientes e dispositivos externos. Clientes e dispositivos externos usam as portas de escuta e publicação de serviços Web externos, normalmente definidos por seu proxy reverso, junto com o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos definidos. O relacionamento do FQDN dos serviços web externos e os URLs Simples definem os endereços do localizador de recursos uniforme (URL) que os clientes externos usarão para acessar os serviços disponíveis para usuários e dispositivos externos. Para obter mais detalhes sobre URLs Simples, consulte [Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls).

  **Servidor de mediação**

- Para **configurar** as propriedades do Servidor de Mediação para um Servidor de Mediação alocado (ou seja, um Servidor de Mediação implantado no Servidor de Front-End ou pool de Front-End), selecione Servidor **de** Mediação Alocado habilitado .

- Para definir as portas **de** escuta para um Servidor de Mediação alocado, digite o valor de porta **TLS** e **TCP** no qual o Servidor de Mediação alocado está escutando. Por padrão, TLS é definido como porta TCP 5067.

- Para definir um valor de porta TCP para o Servidor de Mediação, selecione a caixa de seleção **Habilitar porta TCP.** Por padrão, o Servidor de Mediação usa a segurança da camada de transporte (TLS) sobre o protocolo TCP. As portas TCP estão disponíveis somente quando a seleção Habilitar Porta TCP é habilitada.

    > [!NOTE]
    > Essa é uma configuração opcional, e você deve consultar os requisitos de seu gateway ou PSTN a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

- Defina os troncos associados ao Servidor de Mediação posicionado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.

    Se você tiver mais de um gateway associado a um Servidor de Mediação, poderá especificar o gateway padrão selecionando o gateway que deseja tornar o padrão e clicando em **Tornar Padrão**. Se você escolher remover o gateway padrão, selecione o gateway e clique em **Desfazer Padrão**.

> [!IMPORTANT]
> Se você fizer alterações nas propriedades nesta caixa de diálogo, deverá publicar a topologia e executar o Assistente de Implantação Skype for Business Server em todos os servidores afetados. Depois de publicar a nova topologia, uma lista de servidores afetados onde o Assistente de Implantação Skype for Business Server deve ser executado é fornecida para você como um link na tela de resumo de publicação de topologia bem-sucedida. Para obter detalhes sobre como publicar a topologia atualizada, consulte [Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology). Para obter detalhes sobre o Skype for Business Server de Implantação, consulte [Ferramentas Administrativas do Lync Server.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools)

Clique em **OK** para salvar e confirmar suas alterações no documento de topologia.

Clique **em Cancelar** para descartar suas alterações e feche o pool Editar **Propriedades** para o Servidor front-end ou o pool de front-end.

Clique em **Ajuda** para ler esse tópico de ajuda.

## <a name="see-also"></a>Confira também

[Definir e configurar um pool de front-end ou servidor do Standard Edition](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)