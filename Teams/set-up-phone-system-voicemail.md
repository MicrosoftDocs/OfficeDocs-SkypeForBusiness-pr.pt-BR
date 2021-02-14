---
title: Configurar a caixa postal na nuvem
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
description: 'Saiba como configurar a Caixa Postal na Nuvem para seus usuários. '
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662206"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a caixa postal na nuvem

Este artigo é destinado ao administrador do Microsoft 365 [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) ou do Office 365 conforme descrito em Sobre funções de administrador que querem configurar o recurso Caixa Postal na Nuvem para todos na empresa.

> [!NOTE]
> A Caixa Postal na Nuvem é compatível com o depósito de mensagens de voz somente em uma caixa de correio do Exchange e não dá suporte a sistemas de email de terceiros. 

> [!NOTE]
> Quando um representante atende uma chamada em nome de um delegador, as notificações não estão disponíveis na Caixa Postal da Nuvem. Os usuários podem receber notificações de chamadas perdidas.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Ambientes somente na nuvem: Configurar a Caixa Postal na Nuvem para usuários do Sistema Telefônico Online

Para usuários do Sistema Telefônico Online, **a** Caixa Postal na Nuvem é configurada e provisionada automaticamente para os usuários depois que você atribui uma licença do Sistema de Telefonia aos usuários. 

> [!NOTE]
> Para usuários do Sistema Telefônico Do Skype for Business Online com números de telefone fornecidos localmente, talvez seja necessário habilitar a caixa postal hospedada com [Set-CsUser -HostedVoicemail $True.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar a caixa postal na nuvem para usuários da caixa de correio do Exchange Server

As informações a seguir são sobre como configurar a Caixa Postal da Nuvem para trabalhar com usuários que estão online para o Sistema de Telefonia, mas têm suas caixas de correio no Exchange Server. 
  
1. As mensagens de voz são entregues na caixa de correio do Exchange dos usuários por meio de SMTP roteado pela Proteção do Exchange Online. Para habilitar a entrega bem-sucedida dessas mensagens, verifique se os Conectores do Exchange estão configurados corretamente entre os servidores Exchange e a Proteção do Exchange Online; [Use conectores para configurar o fluxo de email.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Para habilitar recursos de caixa postal, como personalização de saudações e caixa postal visual em clientes do Skype for Business, é necessária conectividade do Microsoft 365 ou do Office 365 com a caixa de correio do servidor Exchange por meio do Exchange Web Services. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação do Exchange Oauth descrito em Configurar autenticação [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)entre as organizações do Exchange e do Exchange Online ou executar o Assistente Híbrido do Exchange a partir do Exchange 2013 CU5 ou superior. Além disso, você deve configurar a integração e o Oauth entre o Skype for Business Online e o servidor Exchange descritos em Configurar Integração e [OAuth entre o Skype for Business Online e o Exchange Server.](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurar a caixa postal na nuvem para usuários do Skype for Business Server

Para configurar os usuários do servidor Skype for Business para a Caixa Postal na Nuvem, consulte o serviço Planejar Caixa Postal na Nuvem [para usuários locais.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Habilitando a caixa postal protegida em sua organização

Quando alguém deixa uma mensagem de voz para um usuário em sua organização, a caixa postal é entregue na caixa de correio do usuário como um anexo de mensagem de email. Usando regras de fluxo de email para aplicar criptografia de mensagens, você pode impedir que essas mensagens de voz seja encaminhadas para outros destinatários. Quando você habilita a caixa postal protegida, os usuários podem ouvir mensagens de voz protegidas ligando para sua caixa postal ou abrindo a mensagem no Outlook, no Outlook na Web ou no Outlook para Android ou iOS. As mensagens de voz protegidas não podem ser abertas no Skype for Business ou no Microsoft Teams.

Para obter mais informações sobre criptografia de mensagem, consulte [Criptografia de email.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Para configurar a caixa postal protegida, faça o seguinte:

1. Acesse e https://admin.microsoft.com entre usando uma conta com permissões de administrador global.
2. Selecione **Mostrar tudo e** vá para Centros de administração **do**  >  **Exchange.**
3. No Centro de Administração do Exchange, selecione **Regras de Fluxo de**  >  **Email.**
4. Selecione **+** **Adicionar** e, em seguida, **aplique Criptografia de Mensagem do Office 365** e proteção de direitos às mensagens.
5. Forneça um nome para a nova regra de fluxo de email e, em Seguida, em Aplicar esta regra, selecione As propriedades da mensagem Incluir o tipo de mensagem  >    >  **Caixa postal.** Selecione **OK.**
6. Em **Fazer o seguinte,** selecione Aplicar Criptografia de Mensagem do **Office 365** e proteção de direitos à mensagem com e selecione **Selecione uma.** Em **modelo RMS,** selecione **Não encaminhar.** Selecione **OK** e, em **seguida, Salvar.**
    > [!NOTE]
    > Se a **lista de modelos rms** estiver vazia, você precisará configurar a Criptografia de Mensagens. Para obter mais informações sobre como configurar a Criptografia de Mensagens, consulte os seguintes artigos:
    > - [Configurar novos recursos de Criptografia de Mensagem](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configurando e gerenciando modelos para a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Opção Não Encaminhar para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

> [!WARNING]
> Para clientes do Skype for Business, desabilitar a caixa postal por meio de uma política de chamada do Microsoft Teams também pode desabilitar o serviço de caixa postal para os usuários do Skype for Business.

A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

As mensagens de voz recebidas pelos usuários em sua organização são transcritas na região onde sua organização do Microsoft 365 ou do Office 365 está hospedada. A região onde seu locatário está hospedado pode não ser a mesma região onde o usuário que recebe a mensagem de voz está localizado. Para exibir a região onde seu locatário [](https://go.microsoft.com/fwlink/p/?linkid=2067339) está hospedado, vá para a página de perfil da Organização e clique em Exibir detalhes **ao** lado de Local **de dados.**

> [!IMPORTANT]
> Não é possível criar uma nova instância de política para mascaramento de transcrição e transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal. Para ver todas as instâncias de política de caixa postal disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798311.aspx)

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desativação da transcrição para sua organização

Como a configuração padrão para transcrição está ínteque para sua organização, talvez você queira desabilitá-la usando [Set-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798310.aspx) Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Ativação do mascaramento de obscenidades para sua organização

Mascaramento de obscenidades está desativado por padrão para sua organização. Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desativação da transcrição para usuário

As políticas de usuário são avaliadas antes das configurações organizacionais padrão. Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798309.aspx)

Para desabilitar a transcrição para um único usuário, execute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Ativação do mascaramento de obscenidades para um usuário

Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Para habilitar o mascaramento de obscenidades para um único usuário, execute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> O serviço de caixa postal no Microsoft 365 e no Office 365 armazena em cache políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ajude os usuários a conhecer os recursos de caixa postal do Teams

Temos as seguintes informações para seus usuários sobre como gerenciar suas configurações de caixa postal, bem como outros recursos de chamada no Teams:

- [Gerencie suas configurações de chamada no Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) Este artigo explica como gerenciar todos os recursos de chamada do Teams do usuário final. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business

Temos informações de treinamento e artigos para ajudar seus usuários a serem bem-sucedidos com a caixa postal do Skype for Business. Indique os seguintes artigos:

- Verifique a caixa postal e as opções do [Skype for Business:](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)este artigo explica como ouvir sua caixa postal no Skype for Business, alterar a saudação da caixa postal, alterar as configurações da caixa postal e ouvir sua caixa postal em velocidades diferentes.

- [Treinamento do Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Plano de migração para o Skype for Business Server e Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
