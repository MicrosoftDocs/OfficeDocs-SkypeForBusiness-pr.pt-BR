---
title: Expansor de configurações gerais do servidor de mediação do Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Você editar as propriedades dos servidores de mediação nessa caixa de diálogo. No lado esquerdo é um conjunto de links rápidos para orientá-lo às definições de configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção são as seguintes configurações:'
ms.openlocfilehash: bc26a6b92746e2cf1453d9ee789500011469527f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375968"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de configurações gerais do servidor de mediação do Lync Server 2010

Você editar as propriedades dos servidores de mediação nessa caixa de diálogo. No lado esquerdo é um conjunto de links rápidos para orientá-lo às definições de configurações gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção são as seguintes configurações:

 **Geral**:

- **FQDN**: editar o nome de domínio totalmente qualificado do servidor de mediação

- **Associações**: marque a caixa de seleção **associar pool de borda (para componentes de mídia)** e selecione um servidor de borda ou o pool de borda para o servidor de mediação para usar como o caminho de mídia para acesso externo.

  **Próximo salto**:

- **Seleção do próximo salto**: selecione em uma lista ao pool do servidor Front-End ou Front-End para usar como o caminho para o servidor de mediação a ser usado para comunicação com sua implantação.

  **Gateway PSTN**:

  **Gateway PSTN do servidor de mediação**:

- **Portas de escuta**: definir as portas que o servidor de mediação escutará. Você pode definir uma porta para segurança de camada de transporte ou **TLS** ou **TCP**, ou o protocolo de controle de transporte. Para a entrada de porta para TCP esteja disponível, você deve selecionar a caixa de seleção para **Habilitar TCP porta**.

    > [!IMPORTANT]
    > Consulte as configurações de documentação e configuração de seu gateway PSTN (rede) telefônica pública comutada para determinar se você precisa habilitar e definir valores de portas TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN. Nem todos os gateways PSTN suportam TLS.

- Uma lista de troncos SIP e gateways que são definidos e configurados para sua implantação está listada. Se nenhuma entrada estiverem presente, não existem configurados para sua implantação de gateways PSTN ou troncos SIP. Definir e configurar gateways em **Componentes compartilhados** e troncos no construtor de topologia.

## <a name="see-also"></a>Consulte também

[Visão geral dos troncos SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opções de implantação de Gateway PSTN](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)