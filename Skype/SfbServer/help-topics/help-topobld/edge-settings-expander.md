---
title: Expansor de Configurações de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:'
ms.openlocfilehash: 28d998986f21e089b34c9a58b9acb238c2aa8ab3108296566ce14210c87220d7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281114"
---
# <a name="edge-settings-expander"></a>Expansor de Configurações de Borda

Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:

- Configurações gerais

- Configurações de seleção de próximo salto

- Configuração do Servidor de Borda



## <a name="general-settings"></a>Configurações gerais

FQDN (nome de domínio totalmente qualificado) de pool interno do pool de Servidor de Borda. Edite o FQDN do pool para alterar essa configuração.

Marque a caixa de seleção Habilitar federação para esse pool de Borda **(Porta 5061)** se você configurar a federação com um parceiro confiável do Lync Server 2013, microsoft Lync Server 2010 ou Microsoft Office Communications Server 2007 R2.

Selecione **Habilitar federação XMPP para este pool de Bordas** para habilitar a federação XMPP.

Especifique o número da porta para **Porta de Replicação de Configuração Interna (HTTPS)**.

## <a name="next-hop-selection-settings"></a>Configurações de seleção de próximo salto

Para definir ou modificar o **pool** de Próximo salto que os Servidores de Borda usarão para se comunicar com a infraestrutura interna, selecione um diretor, pool de diretores, servidor front-end ou pool de Servidor de Front-End na caixa de listagem lista listada. Somente Diretores ou Front Ends configurados no Construtor de Topologias serão exibidos para seleção.

## <a name="edge-server-configuration"></a>Configuração do Servidor de Borda

Para editar ou especificar definições para **Definições Externas** para os Servidores de Borda, você deve determinar, primeiro, se você utilizará endereços IP separados para serviço de Áudio/Vídeo, acesso SIP e webconferência.

Caso pretenda usar endereços IP separados para cada, marque a caixa de seleção  **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve possuir um registro de host DNS (A) correspondente criado para ele.

Para cada um dos serviços externamente focados, você especifica um FQDN e uma porta associada. Por exemplo, o   **Acesso SIP** utilizaria sip.contoso.com e 5061 como porta associada.

> [!IMPORTANT]
> Caso você selecione FQDNs separados para cada um dos serviços externamente focados, cada serviço deve ter um valor de porta único associado a ele. Por padrão, o SIP está na porta 5061/TLS, o serviço de borda de webconferência está na porta 444/TLS e o Servidor de Conferência A/V está na porta 443/TLS. Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externamente focados, limpe a caixa de seleção  **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você então pode editar o pool FQDN de  **Acesso SIP** e valores de porta, se necessário.

> [!IMPORTANT]
> Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

## <a name="see-also"></a>Confira também

Para maiores detalhes sobre como definir e configurar as definições para os Serviços de Borda, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).