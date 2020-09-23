---
title: Expansor de Configurações Gerais de Front End para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Edite as propriedades do servidor front-end ou do pool de front-ends editando ou configurando os seguintes atributos. A página de configuração é separada nas seguintes seções:'
ms.openlocfilehash: 6d7cdb9067ff88b383077538e38c39c2f8e86a5a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219092"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de Configurações Gerais de Front End para Lync Server 2010

Edite as propriedades do servidor front-end ou do pool de front-ends editando ou configurando os seguintes atributos. A página de configuração é separada nas seguintes seções:

 **Geral**

- **FQDN**: o nome de domínio totalmente qualificado do servidor front-end ou do pool de front-ends.

- Selecione **usar todos os endereços IP configurados** para usar todos os endereços configurados no servidor front-end ou no pool de front-ends.

    > [!IMPORTANT]
    > Você não deve selecionar essa opção se colocar o servidor de mediação no servidor front-end ou no pool de front-ends. Servidores de mediação e servidores front-end precisam de endereços IP dedicados nos quais se comunicar.

- Selecione **limitar o uso do serviço para os endereços IP selecionados** e digite o endereço IP do **endereço IP principal** para a comunicação do servidor front-end ou do pool de front-ends com o restante da implantação. Digite o **endereço IP PSTN** o endereço IP que está associado ao servidor de mediação.

    **Recursos e funcionalidade**

- **Conferência**: marque a caixa de seleção se você quiser recursos de conferência em sua implantação. A conferência inclui áudio, vídeo, compartilhamento de aplicativo, compartilhamento de desktop e conferência da Web. Você precisará criar e associar um servidor do Office Web Apps para webconferência (definido mais tarde nesta página de propriedades).

- Se você selecionou Conferência, será possível selecionar **Conferência discada (PSTN)**. Marque a caixa de seleção para habilitar os recursos de conferência discada.

- Marque a caixa de seleção **Enterprise Voice** se você pretende implantar recursos para permitir que o Lync Server 2013 atue como seu sistema de voz telefônica usando tecnologias de voz sobre IP (VoIP) incluindo a opção de implantação de telefones de monofone, troncos SIP ou conectividade de rede telefônica pública comutada usando servidor de mediação, gateways PSTN e IP-PBX, em combinação ou sozinho, com base no design e nos requisitos. Para obter detalhes sobre o Enterprise Voice, consulte [Enterprise Voice](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) e [Plan for Enterprise Voice no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associação**

- **Repositório do SQL Server**: o FQDN do SQL Server (e, opcionalmente, uma instância nomeada) associado ao servidor front-end ou ao pool de front-ends. Selecione o SQL Server store na lista ou crie um novo SQL Server store clicando em **Novo**

- **Repositório de arquivos**: selecione o FQDN do servidor e o compartilhamento (no formato  `\\<FQDN of server>\<share name>` ) que atuará como o local do repositório de arquivos para os arquivos compartilhados que o Lync Server 2013 cria e usa para replicação, diretórios de conferência e outros fins. Selecione o Repositório de arquivo na lista ou crie um novo Repositório de arquivo clicando em **Novo**

- Marque a caixa de seleção **associar servidor de arquivamento** para habilitar um servidor de arquivamento para este servidor front-end ou pool de front-ends. Depois de marcar a caixa de seleção, selecione um servidor de arquivamento existente na lista ou clique em **novo** para criar as definições para um novo servidor de arquivamento.

- Selecione a caixa de seleção **associar servidor de monitoramento** para habilitar um servidor de monitoramento para este servidor front-end ou pool de front-ends. Depois de marcar a caixa de seleção, selecione um servidor de monitoramento existente na lista ou clique em **novo** para criar as definições de um novo servidor de monitoramento.

- Marque a caixa de seleção **associar pool de borda (para componentes de mídia** para habilitar um servidor de borda para este servidor front-end ou pool de front-ends. Depois de marcar a caixa de seleção, selecione um servidor de borda ou pool existente na lista ou clique em **novo** para criar as definições de um novo servidor de borda ou pool.

  **Resiliency**

- Marque a caixa de seleção **pool de registrador de backup associado** para selecionar na lista um servidor front-end ou um pool de front-ends que será o registrador de backup (ou seja, o servidor front-end ou o pool de front-ends designado como registrador secundário em caso de falha do principal)

- Se você selecionou Pool associado de Registradores de backup e escolheu um registrador de backup, poderá marcar a caixa de seleção para **Failover e failback automático para Voz**. Agora é possível definir as propriedades numéricas para **Detecção interna de failover de voz (seg.)** e **Intervalo de failback de voz (seg.)**. Para obter detalhes, consulte [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Serviços Web**

- Para configurar os **Serviços internos da Web**, defina as **Portas de escuta** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Configure também as **Portas publicadas** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Com base em sua configuração de serviços Web internos e uso dos balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga DNS), ajuste os valores de porta para definir as portas de escuta e de publicação.

    > [!IMPORTANT]
    > Os serviços internos da Web e as portas definidas de escuta e publicação servem para clientes e dispositivos internos. Clientes e dispositivos externos usam as portas de escuta e publicação de serviços Web externos, junto com o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos definidos.

- Para configurar os **Serviços Externos da Web**, defina as **Portas de escuta** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Configure também as **Portas publicadas** para **HTTP** e **HTTPS**. Por padrão, são as portas TCP 80 e TCP 443, respectivamente. Com base em sua configuração de serviços Web internos e uso dos balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga DNS), ajuste os valores de porta para definir as portas de escuta e de publicação.

    > [!IMPORTANT]
    > Os serviços externos da Web e as portas definidas de escuta e publicação servem para clientes e dispositivos externos. Clientes e dispositivos externos usam as portas de escuta e publicação de serviços Web externos, normalmente definidos por seu proxy reverso, junto com o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos definidos. O relacionamento do FQDN dos serviços web externos e os URLs Simples definem os endereços do localizador de recursos uniforme (URL) que os clientes externos usarão para acessar os serviços disponíveis para usuários e dispositivos externos. Para obter mais detalhes sobre URLs Simples, consulte [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Servidor de mediação**

- Para configurar as propriedades do **servidor de mediação** para um servidor de mediação posicionado (ou seja, um servidor de mediação implantado no servidor front-end ou no pool de front-ends), selecione **servidor de mediação posicionado habilitado**.

- Para definir as **portas de escuta** de um servidor de mediação posicionado, digite o valor da porta **TLS** e **TCP** no qual o servidor de mediação posicionado está escutando. Por padrão, TLS é definido como porta TCP 5067.

- Para definir um valor de porta TCP para o servidor de mediação, marque a caixa de seleção **habilitar porta TCP** . Por padrão, o servidor de mediação usa o protocolo TLS (Transport Layer Security) sobre TCP. As portas TCP estão disponíveis somente quando a seleção Habilitar Porta TCP é habilitada.

    > [!NOTE]
    > Essa é uma configuração opcional, e você deve consultar os requisitos de seu gateway ou PSTN a fim de determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

- Defina os troncos associados ao Servidor de Mediação posicionado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.

    Se houver mais de um gateway associado a um servidor de mediação, você poderá especificar o gateway padrão selecionando o gateway que deseja tornar o padrão e clicando em **tornar padrão**. Se você escolher remover o gateway padrão, selecione o gateway e clique em **Desfazer Padrão**.

> [!IMPORTANT]
> Se você fizer alterações nas propriedades nessa caixa de diálogo, deverá publicar a topologia e executar o assistente de implantação do Skype for Business Server em todos os servidores afetados. Após publicar a nova topologia, uma lista de servidores afetados onde o assistente de implantação do Skype for Business Server deve ser executado é fornecida como um link na tela Resumo da publicação de topologia bem-sucedida. Para obter detalhes sobre como publicar a topologia atualizada, consulte [Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Para obter detalhes sobre o assistente de implantação do Skype for Business Server, consulte [Ferramentas administrativas do Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Clique em **OK** para salvar e confirmar suas alterações no documento de topologia.

Clique em **Cancelar** para descartar suas alterações e fechar as **Propriedades de edição** para o servidor front-end ou o pool de front-ends.

Clique em **Ajuda** para ler esse tópico de ajuda.

## <a name="see-also"></a>Confira também

[Definir e configurar um pool de front-end ou servidor do Standard Edition](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
