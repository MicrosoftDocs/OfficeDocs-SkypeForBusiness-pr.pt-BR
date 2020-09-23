---
title: Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010
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
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Edite as propriedades dos servidores de mediação nesta caixa de diálogo. Ao longo do lado esquerdo, há um conjunto de links rápidos que levam você às configurações para configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:'
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215152"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010

Edite as propriedades dos servidores de mediação nesta caixa de diálogo. Ao longo do lado esquerdo, há um conjunto de links rápidos que levam você às configurações para configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:

 **Geral**:

- **FQDN**: você edita o nome de domínio totalmente qualificado do servidor de mediação

- **Associações**: marque a caixa de seleção **associar pool de borda (para componentes de mídia)** e selecione um servidor de borda ou um pool de borda para o servidor de mediação usar como o caminho de mídia para acesso externo.

  **Próximo salto**:

- **Seleção do próximo salto**: selecione de uma lista o servidor front-end ou o pool de front-ends a ser usado como o caminho para o servidor de mediação usar para a comunicação com sua implantação.

  **Gateway PSTN**:

  **Gateway PSTN do servidor de mediação**:

- **Portas de escuta**: defina as portas nas quais o servidor de mediação escutará. É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol. Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**.

    > [!IMPORTANT]
    > Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN. Nem todos os gateways PSTN suportam TLS.

- Uma lista de troncos SIP e os gateways definidos e configurados para sua implantação são listados. Se nenhuma entrada estiver presente, não haverá troncos SIP ou gateways PSTN configurados para sua implantação. Você define e configura troncos e gateways em **componentes compartilhados** no construtor de topologias.

## <a name="see-also"></a>Confira também

[Visão geral dos troncos SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opções de implantação do gateways PSTN](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
