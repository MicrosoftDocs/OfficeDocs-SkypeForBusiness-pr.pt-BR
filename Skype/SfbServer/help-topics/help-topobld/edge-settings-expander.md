---
title: Expansor de Configurações de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:'
ms.openlocfilehash: 307a861814a8e05065c70299b5ef2a82c20c8c42
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282528"
---
# <a name="edge-settings-expander"></a>Expansor de Configurações de Borda

Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:

- Configurações gerais

- Configurações de seleção de próximo salto

- Configuração do Servidor de Borda



## <a name="general-settings"></a>Configurações gerais

FQDN (nome de domínio totalmente qualificado) de pool interno do pool de Servidor de Borda. Edite o FQDN do pool para alterar essa configuração.

Marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** se você for configurar a Federação com um servidor do Lync 2013, Microsoft lync Server 2010 ou Microsoft Office Communications Server 2007 R2 Trusted Partner.

Selecione  **Habilitar federação XMPP para este pool de Borda** para habilitar a federação XMPP.

Especifique o número da porta para **Porta de Replicação de Configuração Interna (HTTPS)**.

## <a name="next-hop-selection-settings"></a>Configurações de seleção de próximo salto

Para configurar ou modificar o **Pool de próximo salto** que os Servidores de Borda utilizarão para se comunicar com a infraestrutura interna, selecione um Diretor, pool de Diretores, Servidor Front-Ends ou pool de Servidor Front-Ends na lista suspensa. Somente os directors ou front-ends que foram configurados no construtor de topologias aparecerão para seleção.

## <a name="edge-server-configuration"></a>Configuração do Servidor de Borda

Para editar ou especificar as configurações das **Configurações Externas** de Servidores de Borda, é possível determinar primeiro se você utilizará endereços IP separados para o acesso SIP, webconferência e serviço de Áudio/Vídeo.

Caso pretenda usar endereços IP separados para cada, marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve ter um registro de host DNS (A) correspondente criado para ele.

Especifique um FQDN e uma porta associada para cada um dos serviços externos. Por exemplo, o **Acesso SIP** utilizaria sip.contoso.com e 5061 como porta associada.

> [!IMPORTANT]
> Caso você selecione FQDNs separados para cada um dos serviços externos, cada serviço deve ter um valor de porta único associado a ele. Por padrão, SIP está na porta 5061/TLS, o serviço de borda de webconferência está na porta 444/TLS e o Servidor de Conferência A/V está na porta 443/TLS. Se alterar alguma destas configurações, incluindo usar FQDN e endereços IP ou portas separadas, você deverá atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externos, desmarque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você poderá então editar o FQDN de pool e os valores de porta do **Acesso SIP**, se for necessário.

> [!IMPORTANT]
> Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

## <a name="see-also"></a>Confira também

Para obter detalhes sobre como definir e configurar serviços de Borda, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


