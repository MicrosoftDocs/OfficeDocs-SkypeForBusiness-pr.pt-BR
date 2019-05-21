---
title: Expansor de Configurações Gerais de Front End para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Edite as propriedades do servidor front-end ou do pool de front-end editando ou configurando os atributos a seguir. A página de configuração é separada nas seguintes seções:'
ms.openlocfilehash: b0ee8a2d0081d937bf93d4a638e4f56b1cc79134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284400"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de Configurações Gerais de Front End para Lync Server 2010

Edite as propriedades do servidor front-end ou do pool de front-end editando ou configurando os atributos a seguir. A página de configuração é separada nas seguintes seções:

 **Geral**

- **FQDN**: o nome de domínio totalmente qualificado do servidor front-end ou pool de front-end.

- Selecione **usar todos os endereços IP** configurados para usar todos os endereços configurados no servidor front-end ou no pool de front-end.

    > [!IMPORTANT]
    > Você não deve selecionar essa opção se colocar o servidor de mediação no servidor front-end ou no pool de front-ends. Os servidores de mediação e servidores front-end precisam de endereços IP dedicados para se comunicar.

- Selecione **limitar o uso do serviço para endereços IP selecionados** e insira o endereço IP do **endereço IP primário** para a comunicação do servidor front-end ou do pool de front-end com o restante da implantação. Digite o **endereço IP PSTN** o endereço IP que está associado ao servidor de mediação.

    **Recursos e funcionalidades**

- **Conferência**: marque a caixa de seleção se desejar recursos de conferência na sua implantação. A conferência inclui áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho e conferência via Web. Você precisará criar e associar um servidor de Web Apps do Office para webconferência (definido mais tarde nesta página Propriedades).

- Se você selecionou conferência, a **conferência discada (PSTN)** pode ser selecionada. Marque a caixa de seleção para habilitar os recursos de conferência discada.

- Marque a caixa de seleção **Enterprise Voice** se você pretende implantar recursos para habilitar o Lync Server 2013 para atuar como seu sistema de voz usando as tecnologias de voz sobre IP (VoIP), incluindo a opção de implantação de telefones fixos, troncos SIP ou públicos de telefones. conexão de rede telefônica comutada usando o servidor de mediação, gateways PSTN e IP-PBX, em combinação ou sozinha, com base no design e nos requisitos. Para obter detalhes sobre o Enterprise Voice, consulte [Enterprise Voice](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) e [plano para Enterprise Voice no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associações**

- **Repositório do SQL Server**: o FQDN do SQL Server (e opcionalmente uma instância nomeada) associado ao servidor front-end ou ao pool de front-end. Você seleciona a loja do SQL Server na lista ou cria um novo repositório do SQL Server clicando em **novo**

- **Repositório de arquivos**: você seleciona o FQDN do servidor e o compartilhamento (no formato `\\<FQDN of server>\<share name>`) que atuará como o local do repositório de arquivos para os arquivos compartilhados que o Lync Server 2013 cria e usa para replicação, diretórios de conferência e outras finalidades. Você seleciona o repositório de arquivos da lista ou cria um novo repositório de arquivos clicando em **novo**.

- Marque a caixa de seleção **associar servidor** de arquivamento para habilitar um servidor de arquivamento para este servidor front-end ou pool de front-ends. Depois de marcar a caixa de seleção, selecione um servidor de arquivamento existente na lista ou clique em **novo** para criar as definições para um novo servidor de arquivamento.

- Marque a caixa de seleção **associar servidor de monitoramento** para habilitar um servidor de monitoramento para este servidor front-end ou pool de front-ends. Depois de marcar a caixa de seleção, selecione um servidor de monitoramento existente na lista ou clique em **novo** para criar as definições para um novo servidor de monitoramento.

- Marque a caixa de seleção **associar o pool de bordas (para componentes de mídia** para habilitar um servidor de borda para este servidor front-end ou pool de front-ends. Depois de marcar a caixa de seleção, você seleciona um servidor de borda ou um pool existente na lista ou clica em **novo** para criar as definições para um novo servidor de borda ou pool.

  **Resiliência**

- Marque a caixa de seleção pool de registradores de **backup associados** para selecionar na lista um servidor front-end ou um pool de front-end que será o registrador de backup (ou seja, o servidor front-end ou o pool de front-ends designado como registrador secundário caso o principal houver

- Se você tiver selecionado o pool de registradores de backup associado e tiver escolhido um registrador de backup, poderá marcar a caixa de seleção para **failover e failback automáticos de voz**. Agora você pode definir propriedades numéricas para **detecção interna de failover de voz** e **intervalo de failback de voz (s)**. Para obter detalhes, consulte [planejando a resiliência do Enterprise Voice](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Serviços Web**

- Para configurar **Serviços Web internos**, defina **portas de escuta** para **http** e **https**. Por padrão, essas são portas TCP 80 e porta TCP 443, respectivamente. Você também pode configurar as **portas publicadas** para **http** e **https**. Por padrão, essas são portas TCP 80 e porta TCP 443, respectivamente. Com base na configuração interna dos seus serviços Web e no uso de balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga de DNS), ajuste os valores de porta para definir as portas de escuta e publicadas.

    > [!IMPORTANT]
    > Os serviços internos da Web e as portas de escuta e publicadas definidas são para clientes e dispositivos internos. Dispositivos e clientes externos usam as portas ouvinte e portas publicadas de serviços Web externos, juntamente com o nome de domínio totalmente qualificado dos serviços Web externos (FQDN) definido.

- Para configurar **Serviços Web externos**, defina **portas de escuta** para **http** e **https**. Por padrão, essas são portas TCP 80 e porta TCP 443, respectivamente. Você também pode configurar as **portas publicadas** para **http** e **https**. Por padrão, essas são portas TCP 80 e porta TCP 443, respectivamente. Com base na configuração interna dos seus serviços Web e no uso de balanceadores de carga (balanceadores de carga de hardware e balanceamento de carga de DNS), ajuste os valores de porta para definir as portas de escuta e publicadas.

    > [!IMPORTANT]
    > Os serviços Web externos e as portas de escuta e publicadas definidas são para clientes e dispositivos externos. Dispositivos e clientes externos usam as portas de escuta e as portas publicadas de serviços Web externos, geralmente definidas pelo seu proxy reverso juntamente com o nome de domínio totalmente qualificado dos serviços Web externos (FQDN). A relação do FQDN dos serviços Web externos e as URLs simples definem os endereços de URL (Uniform Resource Locator) que os clientes externos usarão para acessar os serviços disponíveis para usuários e dispositivos externos. Para obter mais detalhes sobre URLs simples, consulte [planejando URLs simples](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Servidor de mediação**

- Para configurar as propriedades do **servidor** de mediação para um servidor de mediação posicionado (ou seja, um servidor de mediação implantado no servidor front-end ou no pool Front-end), selecione o **servidor de mediação posicionado habilitado**.

- Para definir as **portas de escuta** para um servidor de mediação posicionado, digite o valor de porta **TLS** e **TCP** no qual o servidor de mediação posicionado está ouvindo. Por padrão, o TLS é definido como a porta TCP 5067.

- Para definir um valor de porta TCP para o servidor de mediação, marque a caixa de seleção **habilitar porta TCP** . Por padrão, o servidor de mediação usa o protocolo TLS (Transport Layer Security) sobre TCP. As portas TCP estão disponíveis apenas quando a seleção Habilitar porta TCP está habilitada.

    > [!NOTE]
    > Essa é uma configuração opcional, e você deve se referir aos requisitos do seu gateway ou PSTN para determinar se precisa disso. Por padrão, o valor de porta TCP é 5068.

- Você define troncos associados ao servidor de mediação posicionado. Se você já tiver definido os troncos, eles estarão disponíveis para associação com o Servidor de Mediação.

    Se você tiver mais de um gateway associado a um servidor de mediação, poderá especificar o gateway padrão selecionando o gateway que deseja tornar o padrão e clicando em **tornar padrão**. Se você optar por remover o gateway padrão atual, selecione o gateway e clique em desmarcar **padrão**.

> [!IMPORTANT]
> Se você fizer alterações nas propriedades nesta caixa de diálogo, deverá publicar a topologia e executar o assistente de implantação do Skype for Business Server em todos os servidores afetados. Após a publicação da nova topologia, uma lista de servidores afetados em que o assistente de implantação do Skype for Business Server deve ser executado é fornecido para você como um link na tela de Resumo de publicação de topologia bem-sucedida. Para obter detalhes sobre como publicar a topologia atualizada, consulte [publicar a topologia](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Para obter detalhes sobre o assistente de implantação do Skype for Business Server, consulte [Ferramentas administrativas do Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Clique em **OK** para salvar e confirmar as alterações no documento de topologia.

Clique em **Cancelar** para descartar suas alterações e fechar as **Propriedades de edição** para o servidor front-end ou o pool de front-ends.

Clique em **ajuda** para ler este tópico da ajuda.

## <a name="see-also"></a>Confira também

[Definir e configurar um pool de front-end ou um servidor Standard Edition](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
