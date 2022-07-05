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
ms.openlocfilehash: 9d6752098ff9dee6294d53fb24f6b7df6ee8e21c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616247"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a Caixa postal na nuvem

Este artigo destina-se aos administradores do Microsoft 365 que desejam configurar Caixa postal na Nuvem para seus usuários.

Caixa postal na Nuvem deposita mensagens de caixa postal na caixa de correio do Exchange de um usuário. Caixa postal na Nuvem não dá suporte a sistemas de email de terceiros. Para Exchange Online requisitos de licenciamento, [confira Exchange Online descrição do serviço](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Para obter mais informações sobre funções de administrador, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Caixa postal na Nuvem provisionamento

Para usuários do Teams, Caixa postal na Nuvem é configurado e provisionado automaticamente. *Uma Telefonia do Microsoft Teams não é necessária para Caixa postal na Nuvem.*

O provisionamento para usuários do Teams não é o mesmo que era para Skype for Business Online. Para Skype for Business Online, o Caixa postal na Nuvem foi configurado e provisionado automaticamente quando os usuários foram atribuídos a uma licença do Sistema de Telefonia e foram Enterprise Voice habilitados pelo sistema de provisionamento.

Para Skype for Business Server usuários locais, o Caixa postal na Nuvem é configurado e provisionado automaticamente. No entanto, você deve configurar o ambiente Skype for Business Server para rotear chamadas para Caixa postal na Nuvem. Para obter mais informações, [consulte o serviço Caixa postal na Nuvem plano para usuários locais](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>Caixa postal na Nuvem armazenamento

Mensagens de caixa postal geradas Caixa postal na Nuvem são entregues e armazenadas na caixa de correio do Exchange do usuário, no Exchange Online ou Exchange Server. Não há armazenamento específico ou adicional para a caixa postal. Os clientes que acessam a caixa postal (por exemplo, Microsoft Outlook, Microsoft Teams ou Skype for Business) fazem isso por meio da caixa de correio do Exchange e das APIs fornecidas.

Uma mensagem de caixa postal contém um arquivo de áudio anexado com as mensagens de voz e a transcrição da caixa postal (se habilitada).

A caixa de correio do Exchange de um usuário armazena todas as saudações gravadas personalizadas. Essas saudações são recuperadas por Caixa postal na Nuvem conforme necessário durante uma chamada de entrada.

## <a name="cloud-voicemail-processing"></a>Caixa postal na Nuvem processamento

A gravação e a transcrição Caixa postal na Nuvem no Microsoft 365 na origem da chamada que está sendo roteada para Caixa postal na Nuvem. Em seguida, a mensagem é entregue à caixa de correio do Exchange do usuário.

Por exemplo, se uma chamada chegar a um usuário de Roteamento Direto não disponível por meio de um Controlador de Borda de Sessão (SBC) na Europa, a gravação e transcrição da caixa postal serão feitas na Europa. Em seguida, a mensagem é entregue à caixa de correio do Exchange do usuário. Para outro exemplo, suponha que um usuário do Teams América do Norte um usuário indisponível do Teams na Europa. Nesse caso, a chamada começa em América do Norte, o processamento ocorre no América do Norte e, em seguida, a caixa postal é entregue à caixa de correio do Exchange do usuário na Europa.

A entrega de uma caixa postal para uma caixa de correio do Exchange é feita usando o protocolo SMTP, como qualquer outro email.

## <a name="manage-cloud-voicemail-for-users"></a>Gerenciar Caixa postal na Nuvem para usuários

Você pode gerenciar o Caixa postal na Nuvem para usuários especificando políticas de caixa postal e definindo configurações de caixa postal.  

- **As políticas de caixa** postal permitem que você gerencie recursos para grupos de usuários. Você pode configurar e atribuir políticas de caixa postal novas ou existentes para recursos como regras de atendimento de chamadas, transcrição de caixa postal, mascaramento de profanidade de transcrição, tradução de transcrição e idioma do prompt do sistema. Para obter informações sobre como gerenciar políticas de caixa postal, consulte [Gerenciar políticas de caixa postal](manage-voicemail-policies.md).

- **As configurações de caixa** postal permitem definir configurações para usuários individuais. Você pode definir configurações como regras de atendimento de chamadas, idioma do prompt, padrão de conversão de texto em fala e saudações de férias. Para obter informações sobre como definir configurações para usuários individuais, consulte [Gerenciar configurações de caixa postal](manage-voicemail-settings.md). Observe que os usuários finais também podem definir essas configurações no cliente do Teams acessando Configurações **-> Chamadas -> Caixa Postal**.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controlar o roteamento de chamadas para Caixa postal na Nuvem

A configuração padrão para todos os usuários provisionados para Caixa postal na Nuvem é permitir o roteamento de chamadas para Caixa postal na Nuvem e permitir que os usuários encaminhem chamadas para Caixa postal na Nuvem.

Você pode controlar se o roteamento de chamadas para Caixa postal na Nuvem é permitido para usuários do Teams usando o centro de administração do Teams ou usando o PowerShell. 

- Para usar o Centro de administração do Teams,  ->  vá para Políticas de Chamada de **Voz ->** adicionar política nova ou editar a política existente - > caixa postal está disponível para roteamento de chamadas de **entrada**.  

- No PowerShell, use o Set-CsTeamsCallingPolicy cmdlet com o parâmetro AllowVoicemail. Para obter mais informações, [consulte Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

  - Se você definir AllowVoicemail como AlwaysDisabled, as chamadas nunca serão roteadas para a caixa postal, independentemente das configurações de encaminhamento de chamada ou não respondidas para um usuário. A caixa postal não está disponível como um encaminhamento de chamadas ou configuração não respondida no Teams.

  - Se você definir AllowVoicemail como AlwaysEnabled, as chamadas sempre serão encaminhadas para a caixa postal quando não forem atendidas após o toque por trinta segundos, independentemente da configuração de encaminhamento de chamadas não respondida para um usuário.

  - Se você definir AllowVoicemail como UserOverride, as chamadas serão encaminhadas para a caixa postal com base no encaminhamento de chamadas e/ou nas configurações não respondidas de um usuário.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurar Caixa postal na Nuvem para trabalhar com usuários locais

Você pode usar Caixa postal na Nuvem para fornecer funcionalidade de caixa postal para usuários que têm caixas de correio em seus Servidores Exchange ou para usuários que estão usando Skype for Business Server.

Esta seção descreve como configurar o Caixa postal na Nuvem para Exchange Server de correio. Para obter informações sobre como configurar o Caixa postal na Nuvem para Skype for Business Server, consulte [o serviço Caixa postal na Nuvem plano para usuários locais](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar o Caixa postal na Nuvem para usuários Exchange Server caixa de correio

As informações a seguir são sobre como Caixa postal na Nuvem para trabalhar com usuários do Teams que têm sua caixa de correio Exchange Server.

1. As mensagens de caixa postal são entregues à caixa de correio do Exchange de um usuário por meio do SMTP roteado por meio Proteção do Exchange Online. Para habilitar a entrega bem-sucedida dessas mensagens, verifique se os Conectores do Exchange estão configurados corretamente entre os servidores Exchange e Proteção do Exchange Online. Para obter mais informações, [consulte Usar conectores para configurar o fluxo de email](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar recursos de Caixa Postal, como personalização de saudações e caixa postal visual em clientes do Teams, você deve configurar a conectividade entre o Microsoft 365 e o Exchange Server caixa de correio. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação Oauth do Exchange descrito em Configurar a autenticação OAuth entre organizações do [Exchange e do Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) ou executar o Assistente Híbrido do Exchange do Exchange 2013 CU5 ou superior. Você também deve configurar a integração e o Oauth entre o Teams e Exchange Server descrito em Configurar Integração e [OAuth entre o Teams e o Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Habilitar a caixa postal protegida em sua organização

Quando alguém deixa uma mensagem de voz para um usuário em sua organização, a caixa postal é entregue à caixa de correio do usuário como um anexo de mensagem de email.

Usando Proteção de Informações do Microsoft Purview, você pode criptografar as mensagens de caixa postal deixadas por chamadores internos e externos. Você também pode impedir que o usuário encaminhe essas mensagens. Esse recurso é compatível com usuários com Exchange Online de correio.

Para criptografar a mensagem de voz, você pode criar um rótulo de confidencialidade. Com o recurso de rotulagem automática, você pode garantir que o rótulo seja aplicado automaticamente às mensagens de caixa postal de entrada.

Quando você habilita a caixa postal protegida, os usuários podem escutar mensagens de caixa postal protegidas abrindo a mensagem no Outlook, no Outlook na Web ou no Outlook para Android ou iOS. As mensagens de voz protegidas não podem ser abertas no Microsoft Teams ou Skype for Business.

Para criar um rótulo de confidencialidade para a caixa postal, [consulte Usar rótulos de confidencialidade](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). Na seção **Criptografia** , escolha **Permitir que os usuários atribuam permissões quando aplicarem o rótulo**. Selecione **No Outlook, imponha uma das restrições a seguir** e, em seguida, selecione a **opção Não Encaminhar** .

Para criar a política de rotulagem automática para aplicar um rótulo de confidencialidade à caixa postal[](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange), consulte Como configurar políticas de rotulagem automática e especificar as seguintes configurações específicas:

- Para **escolher as informações às quais você deseja aplicar esse rótulo**, selecione **Política personalizada**.

- Para **Escolher locais em que você deseja aplicar o rótulo**, selecione **Locais: Exchange para todos os usuários**.

- Para  **configurar regras comuns ou avançadas**, selecione **Regras avançadas**.

- Regras do Exchange:
  - Condições:
    - **O cabeçalho corresponde ao padrão**: Content-Class = Voice-CA
    - **O endereço IP do remetente** é: 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- Para **Escolher um rótulo a ser aplicado automaticamente**, selecione o rótulo de confidencialidade que você criou para a caixa postal na etapa acima.

- Para **obter configurações adicionais de email**, selecione **Aplicar criptografia ao email recebido de fora** da sua organização e especifique o proprietário do Rights Management.

Os intervalos de IP V4 especificados no endereço IP do Remetente se baseiam na lista na ID 12 em [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Para obter mais informações sobre criptografia de mensagens, consulte [Definir regras de fluxo de email para criptografar mensagens de email](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Ajude os usuários a saber mais sobre Caixa postal na Nuvem recursos

Para ajudar os usuários a saber mais sobre como usar e gerenciar Caixa postal na Nuvem recursos, você pode recomendar os seguintes artigos:

- [Verificar sua caixa postal no Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gerenciar suas configurações de chamada no Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
