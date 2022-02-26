---
title: Configurar a Caixa postal na nuvem
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
ms.openlocfilehash: f1645ec9a14a5b201809cbe12219d7b1e437d355
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974468"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a Caixa postal na nuvem

Este artigo é para Microsoft 365 administradores que querem configurar Caixa postal na Nuvem para seus usuários. 

Caixa postal na Nuvem deposita mensagens de caixa postal na caixa de correio Exchange usuário. Caixa postal na Nuvem não dá suporte a sistemas de email de terceiros. Para Exchange Online requisitos de licenciamento, [consulte Exchange Online descrição do serviço](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Para obter mais informações sobre funções de administrador, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Caixa postal na Nuvem provisionamento

Para Teams usuários, Caixa postal na Nuvem é automaticamente configurada e provisionada. *Uma Microsoft Teams Telefone não é necessária para Caixa postal na Nuvem.*

O provisionamento para Teams usuários não é o mesmo para usuários Skype for Business Online. Para usuários Skype for Business Online, o Caixa postal na Nuvem foi automaticamente configurada e provisionada quando os usuários foram atribuídos a uma licença Sistema de Telefonia e foram Enterprise Voice habilitados pelo sistema de provisionamento.

Para Skype for Business Server usuários locais, Caixa postal na Nuvem é automaticamente configurada e provisionada. No entanto, você deve configurar o ambiente Skype for Business Server para rotear chamadas para Caixa postal na Nuvem. Para obter mais informações, consulte [Plan Caixa postal na Nuvem service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail.md). 

## <a name="cloud-voicemail-storage"></a>Caixa postal na Nuvem armazenamento

As mensagens de caixa postal geradas por Caixa postal na Nuvem são entregues e armazenadas na caixa de correio Exchange do usuário, no Exchange Online ou no Exchange Server. Não há armazenamento específico ou adicional para caixa postal. Os clientes que acessam a caixa postal (por exemplo, Microsoft Outlook, Microsoft Teams ou Skype for Business) fazem isso por meio da caixa de correio Exchange e das APIs fornecidas. 

Uma mensagem de caixa postal contém um arquivo de áudio anexado com as mensagens de voz e a transcrição da caixa postal (se habilitada). 

A Exchange caixa de correio de um usuário armazena todas as saudações gravadas personalizadas. Essas saudações são recuperadas por Caixa postal na Nuvem conforme necessário durante uma chamada de entrada. 

## <a name="cloud-voicemail-processing"></a>Caixa postal na Nuvem processamento 

A gravação e transcrição de Caixa postal na Nuvem começa em Microsoft 365 na origem da chamada que está sendo roteada para Caixa postal na Nuvem. Em seguida, a mensagem é entregue à caixa de correio de Exchange do usuário. 

Por exemplo, se uma chamada chegar a um usuário de Roteamento Direto indisponível por meio de um Controlador de Borda de Sessão (SBC) na Europa, a gravação e transcrição da caixa postal serão feitas na Europa. Em seguida, a mensagem é entregue à caixa de correio de Exchange do usuário. Para outro exemplo, suponha que um usuário Teams na América do Norte chama um usuário Teams indisponível na Europa. Nesse caso, a chamada começa na América do Norte, o processamento ocorre na América do Norte e, em seguida, a caixa postal é entregue para a caixa de correio do usuário Exchange na Europa. 

A entrega de uma caixa postal para uma caixa postal Exchange é feita usando o Protocolo SMTP (Simple Mail Transport Protocol) como qualquer outro email. 

## <a name="manage-cloud-voicemail-for-users"></a>Gerenciar Caixa postal na Nuvem para usuários 

Para gerenciar Caixa postal na Nuvem recursos para seus usuários, use o módulo Teams PowerShell da seguinte forma. 

Para gerenciar Caixa postal na Nuvem para grupos de usuários, use o cmdlet [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy). Você pode configurar e atribuir políticas de caixa postal existentes ou novas para recursos como regras de atendimento de chamada, transcrição de caixa postal, mascaramento de profanidade de transcrição, tradução de transcrição e idioma do prompt do sistema. Para obter mais informações, [consulte New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Para gerenciar Caixa postal na Nuvem configurações para usuários individuais, use o cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Caixa postal na Nuvem configurações que você pode aplicar a usuários individuais incluem regras de atendimento de chamada, linguagem de prompt, texto para padrão de fala e saudações de férias. Para obter mais informações, [consulte Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
(Observe que os usuários finais também podem configurar essas configurações no cliente Teams  ->  indo para Configurações **CallsConfigure** ->  **Voicemail**.)

Você também pode desabilitar o Caixa postal na Nuvem para um usuário usando o cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) e definindo o parâmetro VoicemailEnabled como $false. Essa configuração garantirá que Caixa postal na Nuvem não possa mais gravar uma caixa postal para o usuário.



## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controlar o roteamento de chamadas para Caixa postal na Nuvem 

A configuração padrão para todos os usuários provisionados para Caixa postal na Nuvem é permitir o roteamento de chamadas para Caixa postal na Nuvem e permitir que os usuários encaminhem chamadas para Caixa postal na Nuvem. 

Você pode controlar se o roteamento de chamadas Caixa postal na Nuvem para usuários Teams usando o cmdlet Set-CsTeamsCallingPolicy com o parâmetro AllowVoicemail. Para obter mais informações,  [consulteSet-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy.md). 

- Se você definir AllowVoicemail como AlwaysDisabled, as chamadas nunca serão roteadas para a caixa postal, independentemente das configurações de encaminhamento ou sem resposta de chamada para um usuário. A caixa postal não está disponível como uma configuração de encaminhamento de chamada ou sem resposta Teams.  

- Se você definir AllowVoicemail como AlwaysEnabled, as chamadas sempre serão encaminhadas para a caixa postal sem resposta após tocar por trinta segundos, independentemente da configuração de encaminhamento de chamadas sem resposta para um usuário.  

- Se você definir AllowVoicemail como UserOverride, as chamadas serão encaminhadas para a caixa postal com base no encaminhamento de chamadas e/ou configurações sem resposta para um usuário. 



## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurar Caixa postal na Nuvem para trabalhar com usuários locais

Você pode usar Caixa postal na Nuvem para fornecer funcionalidade de caixa postal para usuários que têm caixas de correio em seus servidores Exchange ou para usuários que estão usando Skype for Business Server. 

Esta seção descreve como configurar o Caixa postal na Nuvem para Exchange Server de caixa de correio. Para obter informações sobre como configurar o Caixa postal na Nuvem para Skype for Business Server usuários, consulte [Plan Caixa postal na Nuvem service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar um Caixa postal na Nuvem para Exchange Server de caixa de correio

As informações a seguir são sobre Caixa postal na Nuvem para trabalhar com Teams usuários que têm suas caixas de correio Exchange Server.

1. As mensagens de caixa postal são entregues à caixa de correio Exchange usuário por meio de SMTP roteado por Proteção do Exchange Online. Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de Exchange conectores estão configurados corretamente entre seus servidores Exchange e Proteção do Exchange Online. Para obter mais informações, [consulte Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar recursos de Caixa Postal, como personalização de saudações e caixa postal visual em clientes Teams, você deve configurar a conectividade entre Microsoft 365 e a caixa de correio Exchange Server de correio. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação do Exchange Oauth descrito em [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater. Você também deve configurar a integração e o Oauth entre Teams e Exchange Server descritos em [Configure Integration and OAuth between Teams and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).


## <a name="enable-protected-voicemail-in-your-organization"></a>Habilitar a caixa postal protegida em sua organização

Quando alguém deixa uma mensagem de caixa postal para um usuário em sua organização, a caixa postal é entregue à caixa de correio do usuário como um anexo de mensagem de email. Usando regras de fluxo de emails para aplicar criptografia de mensagens, você pode impedir que essas mensagens de caixa postal seja encaminhada para outros destinatários. Quando você habilita a caixa postal protegida, os usuários podem ouvir mensagens de caixa postal protegidas chamando em suas caixas de correio de caixa postal ou abrindo a mensagem no Outlook, Outlook na Web ou no Outlook para Android ou iOS. As mensagens de caixa postal protegidas não podem ser abertas Skype for Business ou Microsoft Teams.

Para obter mais informações sobre criptografia de mensagens, consulte [Definir regras de fluxo de emails para criptografar mensagens de email](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).



## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Ajude seus usuários a aprender sobre Caixa postal na Nuvem recursos

Para ajudar seus usuários a aprender sobre como usar e gerenciar Caixa postal na Nuvem recursos, você pode recomendar os seguintes artigos: 

- [Verifique sua caixa postal no Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gerenciar suas configurações de chamada em Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
