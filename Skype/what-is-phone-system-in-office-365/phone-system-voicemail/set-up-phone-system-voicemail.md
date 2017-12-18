---
title: "Configurar o correio de voz do sistema telefônico - ajuda da administração"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
description: "Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. "
---

# Configurar o correio de voz do sistema telefônico - ajuda da administração

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Este artigo é para o [Tudo sobre as funções de administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseja configurar o recurso de caixa postal do sistema telefônico para todos da empresa.
  
> [!NOTE]
> Caixa postal do sistema telefônico suporta depositar mensagens da caixa postal apenas em uma caixa de correio do Exchange e não dá suporte a qualquer sistemas de email de terceiros. Como um mecanismo de fallback, caixa postal do sistema telefônico pode reenviar mensagens usando o SMTP, o que significa que os usuários com uma caixa de correio em um sistema de email de terceiros receberão suas mensagens de caixa postal com nenhuma duração do serviço de garantia ou outros recursos de caixa postal, como a alteração suas saudações e outras configurações. 
  
## Ambientes somente na nuvem: configurar o correio de voz do sistema telefônico

Para Skype para usuários Business Online e planos de chamada, correio de voz do sistema telefônico é configurar automaticamente e provisionado para usuários depois que você atribui uma licença de **Sistema telefônico** e um número de telefone a elas.
  
1. Se o recurso de sistema telefônico não está incluído em seu plano, talvez você precise comprar licenças de complemento do **Sistema telefônico**. Talvez você também precise adquirir uma licença do Exchange Online. Consulte [Skype para Business e Teams Microsoft complemento licenciamento](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), o [Atribuir Skype para Business e Teams Microsoft licenças](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas em sua empresa. Depois de fazer isso, eles poderão receber mensagens de caixa postal!
    
3. Suporte para caixa postal transcrição foi adicionado a partir de março de 2017 e é ativado por padrão para todas as organizações e usuários. Você pode desativar transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.
    
## Sistema telefônico com ambientes locais

São as seguintes informações sobre a configuração da caixa postal do sistema telefônico para funcionar com ambientes de chamar planejar locais.
  
1. Se o recurso de sistema telefônico não está incluído em seu plano, talvez você precise comprar licenças de complemento do **Sistema telefônico**. Você também precisa adquirir uma licença do Exchange Online. Consulte [Skype para Business e Teams Microsoft complemento licenciamento](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), o [Atribuir Skype para Business e Teams Microsoft licenças](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas em sua empresa.
    
3. Siga as instruções na seção **permitem aos usuários para voz do sistema telefônico e serviços de correio de voz** da[Configurar o Skype para Business Cloud conector Edition Guia](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Suporte para caixa postal transcrição foi adicionado a partir de março de 2017 e é ativado por padrão para todas as organizações e usuários. Você pode desativar transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.
    
5. Você também pode ver o [correio de voz do Azure PBX suporte para o Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar a entrega de mensagens de caixa postal Azure para usuários de sistema telefônico que tenham um caixas de correio locais.
    
## Configuração de políticas de caixa postal em sua organização

Transcrição de caixa postal está habilitada por padrão para todas as organizações e usuários; No entanto, você pode controlá-la usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e[Conceder-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .
  
> [!IMPORTANT]
> Não é possível criar uma nova instância de política para transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e você não pode remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy**.
  
Você pode gerenciar as configurações de transcrição de seus usuários usando políticas de caixa postal. Para ver todas as instâncias de política de caixa postal disponível, você pode usar o [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)[]()cmdlet.
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### Desativação da transcrição para sua organização

Como a configuração padrão para transcrição está em para sua organização, talvez você queira desativá-lo usando o [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para fazer isso, execute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### Desativação da transcrição para usuário

Políticas de usuário são avaliadas antes as configurações padrão organizacional. Por exemplo, se transcrição de caixa postal está habilitada para todos os seus usuários, você pode atribuir uma política para desabilitar transcrição de um usuário específico, usando o cmdlet [Conceder-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .
  
Para desabilitar a transcrição para um único usuário, execute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas. 
  
## Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business

Temos informações de treinamento e artigos para ajudar os usuários a ter êxito com a caixa postal de Skype for Business. Aponte para os seguintes artigos:
  
- [Verificar a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir a caixa postal no Skype for Business, alterar sua saudação da caixa postal, alterar suas configurações de caixa postal e ouvir a caixa postal em velocidades diferentes.
    
- [Treinamento do Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## Tópicos Relacionados

[Configurar o Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Veja aqui o que você obtém com sistema telefônico no Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system-in-office-365.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

