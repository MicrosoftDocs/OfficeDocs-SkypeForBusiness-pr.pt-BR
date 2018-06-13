---
title: Permitir que os usuários entrar em contato com usuários externos de equipes
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 'Consulte como configurar equipes para permitir que usuários falar com usuários de outra organização ou deixar que fora talk contatos a eles. '
ms.openlocfilehash: af4b6a61117e96fdbdf869b2bf7fc54c286b42f0
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2018
ms.locfileid: "19863373"
---
# <a name="allow-users-to-contact-external-teams-users"></a>Permitir que os usuários entrar em contato com usuários externos de equipes
  
Siga as etapas descritas neste artigo quando:
  
- Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Você deseja as pessoas na sua organização usar equipes para contatar pessoas na empresas específicas fora da sua organização.
    
- Deseja que qualquer pessoa no mundo que usa as equipes possam encontrar e contatá-lo, usando seu endereço de email. Se você e eles usam as configurações padrão, isso funcionará automaticamente. Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicações entre empresas para os usuários
<a name="bk_preview"> </a>

Você deve ter [permissões de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) no Office 365 em ambas as organizações para fazer isso.

![as equipes-30x30.png logotipo](media/teams-logo-30x30.png)**usando as equipes da Microsoft e Skype para Business Admin Center**.
1. No painel de navegação esquerdo, vá para **configurações de toda a organização** > **acesso externo**. 

2. Na parte superior da página de **acesso externo** , ative o **acesso externo**. 

3. Clique em **Salvar**. 

4. Verifique se o administrador na organização do segue as mesmas etapas e insere o domínio para o seu negócio como um domínio permitido.
 
5. **AGUARDE 24 HORAS PARA FAZER O TESTE**. Em qualquer momento que você alterar as configurações das comunicações externas, poderá levar até 24 horas para as alterações serem efetivadas em todos os data centers.

  
## <a name="test-and-troubleshoot"></a>Testar e solucionar problemas
<a name="bk_preview"> </a>

 **O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**
  
Para testar sua configuração, você precisa de um contato em equipes que não está atrás do firewall da empresa.
  
1. Depois que você alterar as configurações de acesso externo, **Aguarde até 24 horas para teste**.
    
2. Pesquisar seu contato em equipes e enviar uma solicitação para o bate-papo.
    
    Se você receber uma mensagem que ele não pôde ser enviado devido à política da empresa, você precisará verificar novamente suas [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Peça ao seu contato lhe enviar uma solicitação para o bate-papo. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).
    
4. Outra maneira para testar se o problema é seu firewall deve ir para um local de wifi não atrás do seu firewall, como um café e use equipes para enviar uma solicitação ao seu contato para o bate-papo. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Como localizar pessoas e ser localizado ao conectar-se com outra empresa
<a name="bk_preview"> </a>

Após habilitar o acesso externo com outros usuários de equipes, seus usuários podem localizar usuários federados de equipes procurando por seu nome de entrada: por exemplo, Rob@contoso.com. Em seguida, será necessário adicionar a pessoa à sua lista de contatos.
  
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Dicas para configurar comunicações com empresas federadas
<a name="bk_preview"> </a>
    
- Quando dois usuários de equipes com domínios do Office 365 estão se comunicando uns com os outros em domínios separados, eles só podem usar os recursos de equipes (por exemplo, conversas de vídeo ou compartilhamento de área de trabalho) que são ativados em ambas as organizações.
    
- Se os usuários de equipes em sua organização é colocado em um In-loco ou retenção de litígio, qualquer conversas de mensagens Instantâneas entre esse usuário e outra Skype para usuários corporativos ou Skype serão salvo no **Itens recuperáveis** em suas caixas de correio. Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.
  
<a name="bk_preview"> </a>
 
