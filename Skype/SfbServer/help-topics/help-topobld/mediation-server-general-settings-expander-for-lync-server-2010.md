---
title: Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Edite as propriedades dos Servidores de Mediação nesta caixa de diálogo. Ao longo do lado esquerdo há um conjunto de links rápidos para levá-lo às configurações para configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:'
ms.openlocfilehash: 3d30ef41a60f9d837e2d80ae3169c299f46af686
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852105"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010

Edite as propriedades dos Servidores de Mediação nesta caixa de diálogo. Ao longo do lado esquerdo há um conjunto de links rápidos para levá-lo às configurações para configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:

 **Geral**:

- **FQDN**: você edita o nome de domínio totalmente qualificado do Servidor de Mediação

- **Associações**: marque a caixa de seleção Associar pool de Borda (para componentes de **mídia)** e selecione um servidor de borda ou pool de Borda para o Servidor de Mediação a ser usado como o caminho de mídia para acesso externo.

  **Próximo salto**:

- **Seleção de próximo salto**: selecione em uma lista o Servidor front-end ou pool de front-end a ser usado como o caminho para o Servidor de Mediação a ser usado para se comunicar com sua implantação.

  **Gateway PSTN**:

  **Gateway PSTN do Servidor de Mediação**:

- **Portas de** escuta : Defina as portas nas quais o Servidor de Mediação escutará. É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol. Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**.

    > [!IMPORTANT]
    > Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o Servidor de Mediação e o gateway PSTN. Nem todos os gateways PSTN suportam TLS.

- Uma listagem de troncos SIP e os gateways que são definidos e configurados para sua implantação está listada. Se nenhuma entrada estiver presente, não haverá troncos SIP ou gateways PSTN configurados para sua implantação. Você define e configura troncos e gateways em **Componentes Compartilhados** no Construtor de Topologias.

## <a name="see-also"></a>Confira também

[Visão geral dos troncos SIP](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[Opções de implantação do gateways PSTN](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)