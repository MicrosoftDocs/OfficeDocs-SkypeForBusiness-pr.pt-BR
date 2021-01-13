---
title: Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Edite as propriedades dos Servidores de Mediação nesta caixa de diálogo. No lado esquerdo há um conjunto de links rápidos para levar você às configurações de Configurações Gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:'
ms.openlocfilehash: db7964826a50f462435769d66ddfab3804462541
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806741"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de Configurações Gerais do Servido de Mediação para Lync Server 2010

Edite as propriedades dos Servidores de Mediação nesta caixa de diálogo. No lado esquerdo há um conjunto de links rápidos para levar você às configurações de Configurações Gerais, configurações de próximo salto e configurações de gateway PSTN. Em cada seção estão as seguintes configurações:

 **Geral**:

- **FQDN**: edite o nome de domínio totalmente qualificado do Servidor de Mediação

- **Associações:** marque a caixa de seleção Associar Pool de Borda (para componentes de **mídia)** e selecione um Servidor de Borda ou pool de Borda para o Servidor de Mediação a ser usado como o caminho de mídia para acesso externo.

  **Próximo salto:**

- **Seleção de próximo** salto: selecione em uma lista o Servidor front-end ou pool de front-end a ser usado como o caminho para o Servidor de Mediação usar para comunicação com sua implantação.

  **Gateway PSTN:**

  **Gateway PSTN do Servidor de Mediação:**

- **Portas de** escuta: defina as portas nas quais o Servidor de Mediação escutará. É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol. Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**.

    > [!IMPORTANT]
    > Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o Servidor de Mediação e o gateway PSTN. Nem todos os gateways PSTN suportam TLS.

- Uma listagem de troncos SIP e gateways definidos e configurados para sua implantação é listada. Se não houver entradas, não haverá troncos SIP ou gateways PSTN configurados para sua implantação. Você define e configura troncos e gateways em **Componentes Compartilhados** no Construtor de Topologias.

## <a name="see-also"></a>Confira também

[Visão geral dos troncos SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opções de implantação do gateways PSTN](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
