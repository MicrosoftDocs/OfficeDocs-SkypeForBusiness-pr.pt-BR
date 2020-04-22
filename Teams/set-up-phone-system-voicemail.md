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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Saiba como configurar o correio de voz na nuvem para seus usuários. '
ms.openlocfilehash: 4f85e8db6f50becb4ae2406e84621c08507e9737
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779727"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a caixa postal na nuvem

Este artigo é para o [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseja configurar o recurso de correio de voz na nuvem para todos os participantes da empresa.

> [!NOTE]
> O correio de voz na nuvem aceita o depósito de mensagens de correio de voz apenas em uma caixa de correio do Exchange e não é compatível com sistemas de email de terceiros. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Ambientes somente de nuvem: configurar o correio de voz na nuvem

Para os usuários do Skype for Business Online e dos planos de chamada, o correio de voz na nuvem é automaticamente configurado e provisionado para os usuários após a atribuição de uma licença do **sistema telefônico** e um número de telefone a ele.
  
1. Se o recurso do sistema de telefonia não estiver incluído no seu plano, talvez seja necessário comprar licenças complementares do **sistema telefônico** . Você também pode precisar comprar uma licença do Exchange Online. Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [atribuir licenças do Microsoft Teams](assign-teams-licenses.md)e licenças do Exchange Online às pessoas de sua empresa. Depois disso, elas poderão receber mensagens de voz!
    
3. O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários. Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.

## <a name="phone-system-with-on-premises-environments"></a>Sistema de Telefonia com ambientes locais

As informações a seguir tratam da configuração do correio de voz em nuvem para trabalhar com ambientes de plano de chamada local.
  
1. Se o recurso do sistema de telefonia não estiver incluído no seu plano, talvez seja necessário comprar licenças complementares do **sistema telefônico** . Você também precisa comprar uma licença do Exchange Online. Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [atribuir licenças do Microsoft Teams](assign-teams-licenses.md)e licenças do Exchange Online às pessoas de sua empresa.
    
3. Siga as instruções correspondentes à solução de chamadas PSTN locais implantadas para os usuários. Para o Cloud Connector Edition, siga as instruções na seção **habilitar usuários para voz do sistema de telefone e serviços de correio de voz** do [guia configurar o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx). Para chamadas PSTN com o Skype for Business Server, siga [habilitar o recurso usuários do Enterprise Voice no local](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises). Para o roteamento direto do Teams, siga a seção **Configurar o número de telefone e habilitar o** recurso de correio de voz empresarial e [Configurar o roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).

4. O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários. Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.

5. As mensagens de correio de voz são entregues à caixa de correio do Exchange do usuário via SMTP roteado por meio do Exchange Online Protection. Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores do Exchange estejam configurados corretamente entre seus servidores Exchange e a proteção do Exchange Online; [Usar conectores para configurar o fluxo de emails](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

6. Para habilitar recursos de correio de voz, como personalizar saudações e correio de voz visual nos clientes Skype for Business, é necessário conectividade do Office 365 para a caixa de correio do Exchange Server via Exchange Web Services. Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação OAuth do Exchange descrito em [Configurar a autenticação OAuth entre as organizações Exchange e Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), ou executar o assistente híbrido do Exchange no Exchange 2013 CU5 ou superior. Além disso, você deve configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server descritos em [Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises). 

> [!NOTE]
> Quando um representante responde a uma chamada em nome de um delegador, as notificações não estão disponíveis no correio de voz na nuvem. Os usuários podem receber notificações de chamadas perdidas.

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

> [!WARNING]
> Para clientes do Skype for Business, desabilitar o correio de voz por meio de uma política de chamadas do Microsoft Teams também pode desabilitar o serviço de correio de voz para seus usuários do Skype for Business.

A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

As mensagens de correio de voz recebidas pelos usuários em sua organização são transcritas na região em que a sua organização do Office 365 está hospedada. A região em que seu locatário está hospedado pode não ser a mesma região em que o usuário que está recebendo a mensagem de correio de voz está localizado. Para exibir a região em que seu locatário está hospedado, vá para a página de [perfil da organização](https://go.microsoft.com/fwlink/p/?linkid=2067339) e clique em **Exibir detalhes** ao lado de **local de dados**.

> [!IMPORTANT]
> Você não pode criar uma nova instância de política para transcrição e o mascaramento de obscenidades de transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não pode remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .

Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal. Para ver todas as instâncias de política de correio de voz disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desativação da transcrição para sua organização

Como a configuração padrão para a transcrição está ativada para sua organização, talvez você queira desabilitá-la usando [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Ativação do mascaramento de obscenidades para sua organização

Mascaramento de obscenidades está desativado por padrão para sua organização. Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desativação da transcrição para usuário

As políticas de usuário são avaliadas antes das configurações organizacionais padrão. Por exemplo, se a transcrição de correio de voz estiver habilitada para todos os seus usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

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
> [!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ajude seus usuários a aprender recursos de caixa postal do teams

Temos as seguintes informações para os usuários sobre como gerenciar suas configurações de correio de voz, bem como outros recursos de chamada no Microsoft Teams:

- [Gerenciar suas configurações de chamada no Microsoft Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Este artigo explica como gerenciar todos os recursos de chamada de equipe do usuário final. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business

Temos informações e artigos de treinamento para ajudar seus usuários a ser bem-sucedidos com o correio de voz do Skype for Business. Indique os seguintes artigos:

- [Verifique a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir o seu correio de voz no Skype for Business, alterar a saudação da sua caixa postal, mudar suas configurações de correio de voz e ouvir o seu correio de voz em diferentes velocidades.

- [Treinamento do Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Plano de migração para o Skype for Business Server e Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

