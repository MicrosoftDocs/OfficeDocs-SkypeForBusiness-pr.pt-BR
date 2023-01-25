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
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Saiba como configurar Caixa postal na Nuvem para seus usuários.
ms.openlocfilehash: c34b95db32906e81f60fc68dff6fce36e5913140
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981796"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a Caixa postal na nuvem

Este artigo é para administradores do Microsoft 365 que desejam configurar Caixa postal na Nuvem para seus usuários.

Caixa postal na Nuvem deposita mensagens de caixa postal na caixa de correio exchange de um usuário. Caixa postal na Nuvem não dá suporte a sistemas de email de terceiros. Para Exchange Online requisitos de licenciamento, consulte [Exchange Online descrição do serviço](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Para obter mais informações sobre funções de administrador, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>provisionamento Caixa postal na Nuvem

Para usuários do Teams, Caixa postal na Nuvem é configurado e provisionado automaticamente. *Uma licença de Telefonia do Microsoft Teams não é necessária para Caixa postal na Nuvem.*

O provisionamento para usuários do Teams não é o mesmo que era para usuários do Skype for Business Online. Para usuários do Skype for Business Online, Caixa postal na Nuvem foi configurado e provisionado automaticamente quando os usuários receberam uma licença do Sistema telefônico e foram Enterprise Voice habilitados pelo sistema de provisionamento.

Para Skype for Business Server usuários locais, Caixa postal na Nuvem é configurado e provisionado automaticamente. No entanto, você deve configurar o ambiente Skype for Business Server para rotear chamadas para Caixa postal na Nuvem. Para obter mais informações, consulte [Planejar Caixa postal na Nuvem serviço para usuários locais](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>armazenamento Caixa postal na Nuvem

As mensagens de caixa postal geradas por Caixa postal na Nuvem são entregues e armazenadas na caixa de correio exchange do usuário, em Exchange Online ou em Exchange Server. Não há armazenamento específico ou adicional para caixa postal. Os clientes que acessam a caixa postal (por exemplo, Microsoft Outlook, Microsoft Teams ou Skype for Business) fazem isso por meio da caixa de correio do Exchange e das APIs fornecidas.

Uma mensagem de caixa postal contém um arquivo de áudio anexado com as mensagens de voz e a transcrição da caixa postal (se habilitada).

A caixa de correio exchange de um usuário armazena todas as saudações gravadas personalizadas. Essas saudações são recuperadas por Caixa postal na Nuvem conforme necessário durante uma chamada de entrada.

## <a name="cloud-voicemail-processing"></a>Caixa postal na Nuvem processamento

A gravação e a transcrição de Caixa postal na Nuvem começam no Microsoft 365 na origem da chamada que está sendo roteada para Caixa postal na Nuvem. Em seguida, a mensagem é entregue na caixa de correio do Exchange do usuário.

Por exemplo, se uma chamada chegar a um usuário de Roteamento Direto indisponível por meio de um SBC (Controlador de Fronteira de Sessão) na Europa, a gravação de caixa postal e a transcrição serão feitas na Europa. Em seguida, a mensagem é entregue na caixa de correio do Exchange do usuário. Para outro exemplo, suponha que um usuário do Teams no América do Norte chame um usuário indisponível do Teams na Europa. Nesse caso, a chamada começa em América do Norte, o processamento ocorre em América do Norte e, em seguida, a caixa postal é entregue na caixa de correio exchange do usuário na Europa.

A entrega de uma caixa de correio para uma caixa de correio do Exchange é feita usando o SMTP (Simple Mail Transport Protocol) como qualquer outro email.

## <a name="manage-cloud-voicemail-for-users"></a>Gerenciar Caixa postal na Nuvem para usuários

Você pode gerenciar Caixa postal na Nuvem para usuários especificando políticas de caixa postal e configurando configurações de caixa postal.  

- **As políticas de caixa postal** permitem gerenciar recursos para grupos de usuários. Você pode configurar e atribuir políticas de caixa postal existentes ou novas para recursos como regras de resposta de chamada, transcrição de caixa postal, mascaramento de palavrões de transcrição, tradução de transcrição e linguagem prompt do sistema. Para obter informações sobre como gerenciar políticas de caixa postal, consulte [Gerenciar políticas de caixa postal](manage-voicemail-policies.md).

- **As configurações de caixa postal** permitem configurar configurações para usuários individuais. Você pode configurar configurações como regras de resposta de chamada, linguagem de prompt, texto em fala padrão e saudações de férias. Para obter informações sobre como configurar configurações para usuários individuais, consulte [Gerenciar configurações de caixa postal](manage-voicemail-settings.md). Observe que os usuários finais também podem configurar essas configurações no cliente do Teams acessando **Configurações -> Chamadas -> Configurar o Voicemail**.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controlar o roteamento de chamadas para Caixa postal na Nuvem

A configuração padrão para todos os usuários provisionados para Caixa postal na Nuvem é permitir o roteamento de chamadas para Caixa postal na Nuvem e permitir que os usuários encaminhem chamadas para Caixa postal na Nuvem.

Você pode controlar se o roteamento de chamadas para Caixa postal na Nuvem é permitido para usuários do Teams usando o centro de administração do Teams ou usando o PowerShell. 

- Para usar o centro de administração do Teams, acesse **Políticas de Chamada** de **Voz** ->  -> adicionar política nova ou editar -> **o Voicemail está disponível para roteamento de chamadas de entrada**.  

- No PowerShell, use o cmdlet Set-CsTeamsCallingPolicy com o parâmetro AllowVoicemail. Para obter mais informações, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

  - Se você definir AllowVoicemail como AlwaysDisabled, as chamadas nunca serão roteadas para a caixa postal — independentemente das configurações de encaminhamento de chamada ou sem resposta para um usuário. A caixa postal não está disponível como uma configuração de encaminhamento de chamada ou sem resposta no Teams.

  - Se você definir AllowVoicemail como AlwaysEnabled, as chamadas serão sempre encaminhadas para a caixa postal sem resposta depois de tocar por trinta segundos , independentemente da configuração de encaminhamento de chamada sem resposta para um usuário.

  - Se você definir AllowVoicemail como UserOverride, as chamadas serão encaminhadas para a caixa postal com base nas configurações de encaminhamento de chamada e/ou sem resposta para um usuário.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurar Caixa postal na Nuvem para trabalhar com usuários locais

Você pode usar Caixa postal na Nuvem para fornecer funcionalidade de email de voz para usuários que têm caixas de correio em seus Servidores do Exchange ou para usuários que estão usando Skype for Business Server.

Esta seção descreve como configurar Caixa postal na Nuvem para usuários de caixa de correio Exchange Server. Para obter informações sobre como configurar Caixa postal na Nuvem para usuários Skype for Business Server, consulte [Planejar Caixa postal na Nuvem serviço para usuários locais](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar Caixa postal na Nuvem para usuários de caixa de correio Exchange Server

As informações a seguir são sobre como configurar Caixa postal na Nuvem para trabalhar com usuários do Teams que têm sua caixa de correio no Exchange Server.

1. As mensagens de correio de voz são entregues na caixa de correio exchange de um usuário por meio do SMTP roteado por Proteção do Exchange Online. Para habilitar a entrega bem-sucedida dessas mensagens, verifique se os Conectores do Exchange estão configurados corretamente entre os servidores do Exchange e Proteção do Exchange Online. Para obter mais informações, consulte [Usar Conectores para configurar o Fluxo de Email](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar recursos do Voicemail, como personalizar saudações e caixa postal visual em clientes do Teams, você deve configurar a conectividade entre o Microsoft 365 e a caixa de correio Exchange Server. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação do Exchange Oauth descrito em [Configurar a autenticação OAuth entre organizações do Exchange e Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) ou executar o Assistente Híbrido do Exchange do Exchange 2013 CU5 ou superior. Você também deve configurar a integração e o Oauth entre o Teams e Exchange Server descritos em [Configurar Integração e OAuth entre o Teams e Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Habilitar a caixa postal protegida em sua organização

Quando alguém deixa uma mensagem de caixa postal para um usuário em sua organização, a caixa postal é entregue na caixa de correio do usuário como um anexo de mensagem de email.

Usando Proteção de Informações do Microsoft Purview, você pode criptografar as mensagens de caixa postal deixadas por chamadores internos e externos. Você também pode impedir que o usuário encaminhe essas mensagens. Esse recurso tem suporte para usuários com caixas de correio Exchange Online.

Para criptografar a mensagem de caixa postal, você pode criar um rótulo de confidencialidade. Com o recurso de rotulagem automática, você pode garantir que o rótulo será aplicado automaticamente às mensagens de caixa postal de entrada.

Quando você habilita a caixa postal protegida, os usuários podem ouvir mensagens de caixa postal protegidas abrindo a mensagem no Outlook, Outlook na Web ou Outlook para Android ou iOS. Mensagens de caixa postal protegidas não podem ser abertas no Microsoft Teams ou Skype for Business.

Para criar um rótulo de confidencialidade para caixa postal, consulte [Usar rótulos de confidencialidade](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). Na seção **Criptografia** , escolha **Permitir que os usuários atribuam permissões quando aplicarem o rótulo**. Selecione **No Outlook, imponha uma das seguintes restrições** e selecione a opção **Não Encaminhar** .

Para criar a política de rotulagem automática para aplicar um rótulo de confidencialidade à caixa postal, consulte [Como configurar políticas de rotulagem automática e especifique](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) as seguintes configurações específicas:

- Para **Escolher informações às quais deseja que esse rótulo seja aplicado**, selecione **Política personalizada**.

- Para **Escolher locais em que você deseja aplicar o rótulo**, **selecione Locais: Trocar por todos os usuários**.

- Para  **Configurar regras comuns ou avançadas**, selecione **Regras avançadas**.

- Regras de troca:
  - Condições:
    - **Padrão de correspondência de cabeçalho**: Classe de conteúdo = Voice-CA
    - **O endereço IP do remetente é**: 13.107.64.0/18, 52.112.0.0/14, 52.122.0.0/15, 52.238.119.141/32, 52.244.160.207/32

- Para **Escolher um rótulo a ser aplicado automaticamente**, selecione o rótulo de confidencialidade que você criou para a caixa postal na etapa acima.

- Para **configurações adicionais para email**, selecione **Aplicar criptografia ao email recebido de fora da sua organização** e especifique o proprietário do Rights Management.

Os intervalos IP V4 especificados no endereço IP do Remetente baseiam-se na lista na ID 12 em [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Para obter mais informações sobre criptografia de mensagens, consulte [Definir regras de fluxo de email para criptografar mensagens de email](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Ajudar seus usuários a aprender sobre Caixa postal na Nuvem recursos

Para ajudar seus usuários a aprenderem sobre como usar e gerenciar recursos Caixa postal na Nuvem, você pode recomendar os seguintes artigos:

- [Verificar sua caixa postal no Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gerenciar suas configurações de chamada no Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
