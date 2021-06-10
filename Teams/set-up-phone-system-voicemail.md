---
title: Configurar a Caixa postal na nuvem
author: dstrome
ms.author: dstrome
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Saiba como configurar o Caixa postal na Nuvem para seus usuários. '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117059"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a Caixa postal na nuvem

Este artigo é para o administrador Microsoft 365 ou Office 365 conforme descrito em [Sobre](/microsoft-365/admin/add-users/about-admin-roles) funções de administrador que deseja configurar o recurso Caixa postal na Nuvem para todos na empresa.

> [!NOTE]
> Caixa postal na Nuvem suporta o depósito de mensagens de caixa postal somente em uma caixa de correio Exchange e não oferece suporte a sistemas de email de terceiros. 

> [!NOTE]
> Quando um representante responde a uma chamada em nome de um representante, as notificações não estão disponíveis Caixa postal na Nuvem. Os usuários podem receber notificações para chamadas perdidas.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Ambientes somente na nuvem: configurar o Caixa postal na Nuvem para usuários Sistema de Telefonia online

Para usuários Sistema de Telefonia online, Caixa postal na Nuvem é automaticamente configurada e provisionada para usuários depois que você atribui uma Sistema de Telefonia **aos** usuários. 

> [!NOTE]
> Para usuários Skype for Business Sistema de Telefonia online com números de telefone fornecidos no local, talvez seja necessário habilitar a caixa postal hospedada com [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps). 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar o Caixa postal na Nuvem para Exchange Server de Caixa de Correio

As informações a seguir são sobre Caixa postal na Nuvem para trabalhar com usuários que estão online para Sistema de Telefonia mas têm sua caixa de correio Exchange Server. 
  
1. As mensagens de caixa postal são entregues à caixa de correio Exchange dos usuários por meio de SMTP roteado por Proteção do Exchange Online. Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores Exchange estão configurados corretamente entre seus servidores Exchange e Proteção do Exchange Online; [Use conectores para configurar o email Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

2. Para habilitar recursos de Caixa Postal, como personalização de saudações e caixa postal visual em clientes Skype for Business, a conectividade do Microsoft 365 ou Office 365 para Exchange caixa de correio do servidor Exchange por meio do Exchange Web Services é necessária. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação do Exchange Oauth descrito em [Configure OAuth authentication between Exchange](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)and Exchange Online organizations , or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater. Além disso, você deve configurar a integração e o Oauth entre o Skype for Business Online e o servidor Exchange descritos em [Configure Integration and OAuth between Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)e Exchange Server . 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurar um Caixa postal na Nuvem para Skype for Business Server Usuários

Para configurar Skype for Business usuários de servidor para Caixa postal na Nuvem, consulte [Plan Caixa postal na Nuvem service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="enabling-protected-voicemail-in-your-organization"></a>Habilitando a caixa postal protegida em sua organização

Quando alguém deixa uma mensagem de caixa postal para um usuário em sua organização, a caixa postal é entregue à caixa de correio do usuário como um anexo de mensagem de email. Usando regras de fluxo de emails para aplicar criptografia de mensagens, você pode impedir que essas mensagens de caixa postal seja encaminhada para outros destinatários. Quando você habilita a caixa postal protegida, os usuários podem ouvir mensagens de caixa postal protegidas ligando para a caixa de correio de caixa postal ou abrindo Outlook mensagem no Outlook, Outlook na Web ou no Outlook para Android ou iOS. As mensagens de caixa postal protegidas não podem ser abertas Skype for Business ou Microsoft Teams.

Para obter mais informações sobre criptografia de mensagens, consulte [Criptografia de email](/microsoft-365/compliance/email-encryption?view=o365-worldwide).

Para configurar a caixa postal protegida, faça o seguinte:

1. Acesse e https://admin.microsoft.com entre usando uma conta com permissões de administrador global.
2. Selecione **Mostrar tudo** e vá para Centros de administração   >  **Exchange**.
3. No Centro de administração Exchange, selecione **Regras de fluxo de**  >  **email**.
4. Selecione **+** **Adicionar** e, em seguida, selecione **Aplicar Criptografia de Mensagens do Office 365 e proteção de direitos a mensagens**.
5. Forneça um nome para a nova regra de fluxo de emails e, em Seguida, em Aplicar essa regra **se**, selecione **As** propriedades da mensagem Incluir o tipo  >  **de** mensagem Caixa  >  **postal**. Selecione **OK**.
6. Em **Fazer o seguinte,** selecione **Aplicar Criptografia de Mensagens do Office 365 proteção de** direitos e direitos à mensagem com e selecione **Selecionar um**. Em **modelo RMS,** selecione **Não encaminhar**. Selecione **OK** **e,** em seguida, Salvar .
    > [!NOTE]
    > Se a **lista de modelos RMS** estiver vazia, você precisará configurar a Criptografia de Mensagens. Para obter mais informações sobre como configurar a Criptografia de Mensagens, consulte os seguintes artigos:
    > - [Configurar novos recursos de Criptografia de Mensagens](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configurando e gerenciando modelos para a Proteção de Informações do Azure](/information-protection/deploy-use/configure-policy-templates)
    > - [Opção Não Encaminhar para emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

> [!WARNING]
> Para Skype for Business clientes, desabilitar a caixa postal por meio de uma política de chamada Microsoft Teams também pode desabilitar o serviço de caixa postal para seus Skype for Business usuários.

A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) e [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy).

As mensagens de caixa postal recebidas pelos usuários em sua organização são transcritas na região onde sua organização Microsoft 365 ou Office 365 está hospedada. A região onde seu locatário está hospedado pode não ser a mesma onde o usuário que recebe a mensagem de caixa postal está localizado. Para exibir a região onde seu locatário [](https://go.microsoft.com/fwlink/p/?linkid=2067339) está hospedado, vá para a página Perfil da Organização e clique em Exibir **detalhes** ao lado de **Data location**.

> [!IMPORTANT]
> Não é possível criar uma nova instância de política para mascaramento de profanidade de transcrição e transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal. Para ver todas as instâncias de política de caixa postal disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
### <a name="turning-off-transcription-for-your-organization"></a>Desativação da transcrição para sua organização

Como a configuração padrão para transcrição está em sua organização, talvez você queira desabilitá-la usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Ativação do mascaramento de obscenidades para sua organização

Mascaramento de obscenidades está desativado por padrão para sua organização. Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desativação da transcrição para usuário

As políticas de usuário são avaliadas antes das configurações organizacionais padrão. Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)

Para desabilitar a transcrição para um único usuário, execute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Ativação do mascaramento de obscenidades para um usuário

Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).

Para habilitar o mascaramento de obscenidades para um único usuário, execute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> O serviço de caixa postal em Microsoft 365 e Office 365 armazena em cache políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ajudar seus usuários a aprender Teams recursos de caixa postal

Temos as seguintes informações para seus usuários sobre como gerenciar suas configurações de caixa postal, bem como outros recursos de chamada em Teams:

- [Gerencie suas configurações de chamada em Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Este artigo explica como gerenciar todos os recursos de chamada Teams usuário final. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business

Temos informações de treinamento e artigos para ajudar seus usuários a serem bem-sucedidos Skype for Business caixa postal. Indique os seguintes artigos:

- [Verifique Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)caixa postal e opções : Este artigo explica como ouvir sua caixa postal no Skype for Business, alterar sua saudação de caixa postal, alterar suas configurações de caixa postal e ouvir sua caixa postal em velocidades diferentes.

- [Treinamento do Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Plano de migração para o Skype for Business Server e Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)