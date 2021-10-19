---
title: Configurar a Caixa postal na nuvem
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Saiba como configurar o Caixa postal na Nuvem para seus usuários.
ms.openlocfilehash: f448ba79c2451383c0ca85916309bdfab3b69a96
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462365"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a Caixa postal na nuvem

Este artigo é para o administrador Microsoft 365 ou Office 365 conforme descrito em [Sobre](/microsoft-365/admin/add-users/about-admin-roles) funções de administrador que deseja configurar o recurso Caixa postal na Nuvem para todos na empresa. Caixa postal na Nuvem requer Exchange caixas de correio para usuários onde ele deposita mensagens de caixa postal. Ele não dá suporte a sistemas de email de terceiros.

## <a name="cloud-voicemail-for-teams-users"></a>Caixa postal na Nuvem para Teams usuários

Para Teams usuários, Caixa postal na Nuvem é automaticamente configurada e provisionada. Uma Microsoft Teams Telefone não é necessária para Caixa postal na Nuvem.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ajudar seus usuários a aprender Teams recursos de caixa postal

Temos as seguintes informações para seus usuários sobre como usar e gerenciar a caixa postal no Teams:

- [Verifique sua caixa postal no Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gerenciar suas configurações de chamada em Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurando Caixa postal na Nuvem para trabalhar com usuários locais

Você pode usar o Caixa postal na Nuvem para fornecer funcionalidade de caixa postal aos usuários que têm caixas de correio em seus servidores Exchange ou para usuários que estão usando Skype for Business Server. Esta seção fornece informações para esses cenários. 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar o Caixa postal na Nuvem para Exchange Server de Caixa de Correio

As informações a seguir são sobre Caixa postal na Nuvem para trabalhar com Microsoft Teams Telefone usuários que têm suas caixas de correio Exchange Server.

1. As mensagens de caixa postal são entregues à caixa de correio Exchange dos usuários por meio de SMTP roteado por Proteção do Exchange Online. Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores Exchange estão configurados corretamente entre seus servidores Exchange e Proteção do Exchange Online; [Use conectores para configurar o email Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar recursos de Caixa Postal, como personalização de saudações e caixa postal visual em clientes Skype for Business, a conectividade do Microsoft 365 ou Office 365 para Exchange caixa de correio do servidor Exchange por meio do Exchange Web Services é necessária. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação do Exchange Oauth descrito em [Configure OAuth authentication between Exchange](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)and Exchange Online organizations , or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater. Além disso, você deve configurar a integração e o Oauth entre o Skype for Business Online e o servidor Exchange descritos em [Configure Integration and OAuth between Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)e Exchange Server .

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurar um Caixa postal na Nuvem para Skype for Business Server Usuários

Para configurar Skype for Business usuários de servidores para Caixa postal na Nuvem, consulte [Plan Caixa postal na Nuvem service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="enabling-protected-voicemail-in-your-organization"></a>Habilitando a caixa postal protegida em sua organização

Quando alguém deixa uma mensagem de caixa postal para um usuário em sua organização, a caixa postal é entregue à caixa de correio do usuário como um anexo de mensagem de email. Usando regras de fluxo de emails para aplicar criptografia de mensagens, você pode impedir que essas mensagens de caixa postal seja encaminhada para outros destinatários. Quando você habilita a caixa postal protegida, os usuários podem ouvir mensagens de caixa postal protegidas chamando em suas caixas de correio de caixa postal ou abrindo a mensagem no Outlook, Outlook na Web ou no Outlook para Android ou iOS. As mensagens de caixa postal protegidas não podem ser abertas Skype for Business ou Microsoft Teams.

Para obter mais informações sobre criptografia de mensagens, consulte [Definir regras de fluxo de emails para criptografar mensagens de email](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).
