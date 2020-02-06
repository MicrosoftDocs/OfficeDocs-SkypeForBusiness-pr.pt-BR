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
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Você edita as propriedades dos servidores de mediação nesta caixa de diálogo. Ao longo do lado esquerdo, há um conjunto de links rápidos para levá-lo às configurações gerais, às próximas configurações de salto e configurações de gateway PSTN. Em cada seção, encontram-se as seguintes configurações:'
ms.openlocfilehash: 3f7dad61778f54fee7a9be984191bc21f5029502
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819613"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010

Você edita as propriedades dos servidores de mediação nesta caixa de diálogo. Ao longo do lado esquerdo, há um conjunto de links rápidos para levá-lo às configurações gerais, às próximas configurações de salto e configurações de gateway PSTN. Em cada seção, encontram-se as seguintes configurações:

 **Geral**:

- **FQDN**: você edita o nome de domínio totalmente qualificado do servidor de mediação

- **Associações**: marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** e selecione um servidor de borda ou um pool de bordas para o servidor de mediação usar como o caminho de mídia para acesso externo.

  **Próximo salto**:

- **Seleção do próximo salto**: selecione em uma lista o servidor front-end ou o pool de front-end a ser usado como o caminho para o servidor de mediação usar para se comunicar com sua implantação.

  **Gateway PSTN**:

  **Gateway PSTN do servidor de mediação**:

- **Portas de escuta**: defina as portas que o servidor de mediação escutará. Você pode definir uma porta para **TLS** ou Transport Layer Security ou **TCP**ou protocolo de controle de transporte. Para que a entrada de porta TCP esteja disponível, você deve marcar a caixa de seleção **habilitar porta TCP**.

    > [!IMPORTANT]
    > Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se você precisa habilitar e definir valores de porta TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN. Nem todos os gateways PSTN dão suporte a TLS.

- Uma lista de troncos SIP e os gateways definidos e configurados para a sua implantação está listada. Se não houver entradas presentes, não há troncos SIP ou gateways PSTN configurados para sua implantação. Você define e configura troncos e gateways em **componentes compartilhados** no construtor de topologias.

## <a name="see-also"></a>Confira também

[Visão geral do entroncamento SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opções de implantação do gateway PSTN](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
