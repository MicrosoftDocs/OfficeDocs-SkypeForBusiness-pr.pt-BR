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
ms.openlocfilehash: 6a75856954da509677a1c9ccdb54e34055f171ed
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681402"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a Caixa postal na nuvem

Este artigo é para Microsoft 365 administradores que desejam configurar Caixa postal na Nuvem para seus usuários.

Caixa postal na Nuvem deposita mensagens de caixa postal na caixa de correio Exchange usuário. Caixa postal na Nuvem não dá suporte a sistemas de email de terceiros. Para Exchange Online requisitos de licenciamento, [confira Exchange Online descrição do serviço](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Para obter mais informações sobre funções de administrador, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Caixa postal na Nuvem provisionamento

Para Teams usuários, Caixa postal na Nuvem é configurado e provisionado automaticamente. *Uma Telefonia do Microsoft Teams não é necessária para Caixa postal na Nuvem.*

O provisionamento Teams usuários não é o mesmo que era para Skype for Business Online. Para Skype for Business Online, o Caixa postal na Nuvem foi configurado e provisionado automaticamente quando os usuários foram atribuídos a uma licença do Sistema de Telefonia e foram Enterprise Voice habilitados pelo sistema de provisionamento.

Para Skype for Business Server usuários locais, o Caixa postal na Nuvem é configurado e provisionado automaticamente. No entanto, você deve configurar o ambiente Skype for Business Server para rotear chamadas para Caixa postal na Nuvem. Para obter mais informações, [consulte o serviço Caixa postal na Nuvem plano para usuários locais](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>Caixa postal na Nuvem armazenamento

Mensagens de caixa postal geradas Caixa postal na Nuvem são entregues e armazenadas na caixa de correio Exchange do usuário, no Exchange Online ou Exchange Server. Não há armazenamento específico ou adicional para a caixa postal. Os clientes que acessam a caixa postal (por exemplo, Microsoft Outlook, Microsoft Teams ou Skype for Business) fazem isso por meio da caixa de correio do Exchange e das APIs fornecidas.

Uma mensagem de caixa postal contém um arquivo de áudio anexado com as mensagens de voz e a transcrição da caixa postal (se habilitada).

A Exchange caixa de correio de um usuário armazena todas as saudações gravadas personalizadas. Essas saudações são recuperadas por Caixa postal na Nuvem conforme necessário durante uma chamada de entrada.

## <a name="cloud-voicemail-processing"></a>Caixa postal na Nuvem processamento

A gravação e a transcrição de Caixa postal na Nuvem começa Microsoft 365 na origem da chamada que está sendo roteada para Caixa postal na Nuvem. Em seguida, a mensagem é entregue à caixa de correio Exchange usuário.

Por exemplo, se uma chamada chegar a um usuário de Roteamento Direto não disponível por meio de um Controlador de Borda de Sessão (SBC) na Europa, a gravação e transcrição da caixa postal serão feitas na Europa. Em seguida, a mensagem é entregue à caixa de correio Exchange usuário. Para outro exemplo, suponha que um Teams usuário no América do Norte chama um usuário Teams indisponível na Europa. Nesse caso, a chamada é iniciada em América do Norte, o processamento ocorre no América do Norte e, em seguida, a caixa postal é entregue à caixa postal do Exchange usuário na Europa.

A entrega de uma caixa postal para uma Exchange de correio é feita usando o protocolo SMTP, como qualquer outro email.

## <a name="manage-cloud-voicemail-for-users"></a>Gerenciar Caixa postal na Nuvem para usuários

Para gerenciar Caixa postal na Nuvem recursos para seus usuários, use o Teams do PowerShell da seguinte maneira.

Para gerenciar Caixa postal na Nuvem recursos para grupos de usuários, use o cmdlet [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).
Você pode configurar e atribuir políticas de caixa postal novas ou existentes para recursos como regras de atendimento de chamadas, transcrição de caixa postal, mascaramento de profanidade de transcrição, tradução de transcrição e idioma do prompt do sistema. Para obter mais informações, [consulte New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Para gerenciar Caixa postal na Nuvem configurações para usuários individuais, use o cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Caixa postal na Nuvem configurações que você pode aplicar a usuários individuais incluem regras de atendimento a chamadas, idioma de prompt, padrão de conversão de texto em fala e saudações de férias. Para obter mais informações, [consulte Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
(Observe que os usuários finais também podem definir essas configurações no cliente Teams acessando **Configurações** ->  **Calls** -> **Configure Voicemail**.)

Você também pode desabilitar o Caixa postal na Nuvem para um usuário usando o cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) e definindo o parâmetro VoicemailEnabled como $false. Essa configuração garantirá que Caixa postal na Nuvem não possa mais gravar uma caixa postal para o usuário.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controlar o roteamento de chamadas para Caixa postal na Nuvem

A configuração padrão para todos os usuários provisionados para Caixa postal na Nuvem é permitir o roteamento de chamadas para Caixa postal na Nuvem e permitir que os usuários encaminhem chamadas para Caixa postal na Nuvem.

Você pode controlar se o roteamento de chamadas para Caixa postal na Nuvem é permitido para Teams usuários usando o cmdlet Set-CsTeamsCallingPolicy com o parâmetro AllowVoicemail. Para obter mais informações, [consulte Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

- Se você definir AllowVoicemail como AlwaysDisabled, as chamadas nunca serão roteadas para a caixa postal, independentemente das configurações de encaminhamento de chamada ou não respondidas para um usuário. A caixa postal não está disponível como um encaminhamento de chamadas ou configuração não respondida no Teams.

- Se você definir AllowVoicemail como AlwaysEnabled, as chamadas sempre serão encaminhadas para a caixa postal quando não forem atendidas após o toque por trinta segundos, independentemente da configuração de encaminhamento de chamadas não respondida para um usuário.

- Se você definir AllowVoicemail como UserOverride, as chamadas serão encaminhadas para a caixa postal com base no encaminhamento de chamadas e/ou nas configurações não respondidas de um usuário.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurar Caixa postal na Nuvem para trabalhar com usuários locais

Você pode usar Caixa postal na Nuvem para fornecer funcionalidade de caixa postal para usuários que têm caixas de correio em seus servidores Exchange ou para usuários que estão usando Skype for Business Server.

Esta seção descreve como configurar o Caixa postal na Nuvem para Exchange Server de correio. Para obter informações sobre como configurar o Caixa postal na Nuvem para Skype for Business Server, consulte [o serviço Caixa postal na Nuvem plano para usuários locais](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar o Caixa postal na Nuvem para usuários Exchange Server caixa de correio

As informações a seguir são sobre como Caixa postal na Nuvem para trabalhar com Teams usuários que têm sua caixa de correio Exchange Server.

1. As mensagens de caixa postal são entregues à caixa de correio Exchange usuário por meio do SMTP roteado por meio Proteção do Exchange Online. Para habilitar a entrega bem-sucedida dessas mensagens, verifique se Exchange conectores estão configurados corretamente entre seus servidores Exchange e Proteção do Exchange Online. Para obter mais informações, [consulte Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar recursos de caixa postal, como personalizar saudações e caixa postal visual em clientes Teams, você deve configurar a conectividade entre Microsoft 365 e a caixa de correio Exchange Server usuário. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação Oauth do Exchange descrito em Configurar a autenticação [OAuth entre organizações do Exchange e do Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) ou executar o Assistente Híbrido do Exchange do Exchange 2013 CU5 ou superior. Você também deve configurar a integração e o Oauth entre Teams e Exchange Server descritos em Configurar Integração e [OAuth entre Teams e Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Habilitar a caixa postal protegida em sua organização

Quando alguém deixa uma mensagem de voz para um usuário em sua organização, a caixa postal é entregue à caixa de correio do usuário como um anexo de mensagem de email.

Usando Proteção de Informações do Microsoft Purview, você pode criptografar as mensagens de caixa postal deixadas por chamadores internos e externos. Você também pode impedir que o usuário encaminhe essas mensagens. Esse recurso é compatível com usuários com Exchange Online de correio.

Para criptografar a mensagem de voz, você pode criar um rótulo de confidencialidade. Com o recurso de rotulagem automática, você pode garantir que o rótulo seja aplicado automaticamente às mensagens de caixa postal de entrada.

Quando você habilita a caixa postal protegida, os usuários podem escutar mensagens de caixa postal protegidas chamando sua caixa postal ou abrindo a mensagem no Outlook, Outlook na Web ou Outlook para Android ou iOS. As mensagens de caixa postal protegidas não podem ser abertas Microsoft Teams ou Skype for Business.

Para criar um rótulo de confidencialidade para a caixa postal, [consulte Usar rótulos de confidencialidade](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). Na seção **Criptografia** , escolha **Permitir que os usuários atribuam permissões quando aplicarem o rótulo**. Selecione **Em Outlook, imponha uma das restrições a seguir** e, em seguida, selecione a **opção Não Encaminhar**.

Para criar a política de rotulagem automática para aplicar um rótulo de confidencialidade à caixa postal[](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange), consulte Como configurar políticas de rotulagem automática e especificar as seguintes configurações específicas:

- Para **escolher as informações às quais você deseja aplicar esse rótulo**, selecione **Política personalizada**.

- Para **Escolher locais em que você deseja aplicar o rótulo**, selecione **Locais: Exchange para todos os usuários**.

- Para  **configurar regras comuns ou avançadas**, selecione **Regras avançadas**.

- Exchange regras:
  - Condições:
    - **O cabeçalho corresponde ao padrão**: Content-Class = Voice-CA
    - **O endereço IP do remetente** é: 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- Para **Escolher um rótulo a ser aplicado automaticamente**, selecione o rótulo de confidencialidade que você criou para a caixa postal na etapa acima.

- Para **obter configurações adicionais de email**, selecione Aplicar criptografia ao **email** recebido de fora da sua organização e especifique o Rights Management proprietário.

Os intervalos de IP V4 especificados no endereço IP do Remetente se baseiam na lista na ID 12 em [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Para obter mais informações sobre criptografia de mensagens, consulte [Definir regras de fluxo de email para criptografar mensagens de email](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Ajude os usuários a saber mais sobre Caixa postal na Nuvem recursos

Para ajudar os usuários a saber mais sobre como usar e gerenciar Caixa postal na Nuvem recursos, você pode recomendar os seguintes artigos:

- [Verifique sua caixa postal Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gerenciar suas configurações de chamada Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
