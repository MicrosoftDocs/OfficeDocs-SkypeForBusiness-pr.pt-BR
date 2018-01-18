---
title: "Permitir que os usuários do Skype for Business adicionem contatos do Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Permitir que os usuários do Skype for Business adicionem contatos do Skype

Com o Skype for Business, os usuários podem pesquisar todos os usuários do Skype (o aplicativo gratuito!) e enviar mensagens instantâneas para eles. Este artigo explica o que você precisa fazer para adicionar contatos do Skype. 
  
Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) no Office 365 para fazer isso.
  
1. Entre com sua conta de administrador do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. No Centro de administração do Office 365, vá para **Centros de Administração** > **Skype for Business**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. No **Skype para centro de administração de negócios**, escolha **organização** > **comunicações externas**. 
    
4. Por padrão, seus usuários podem se comunicar com todas as outras pessoas do mundo que usam Skype for Business (supondo que seu firewall tenha sido configurado para permitir isso). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Se você quer que seus usuários conversem com os usuários do Skype, MAS não quer que eles conversem com usuários que usam o Skype for Business, escolha **Ativado somente para os domínios permitidos**. Quando você habilita o contato com os usuários do Skype, o skype.com é adicionado automaticamente como um domínio permitido nos bastidores. 
    
    Se quiser permitir contato de todas as outras empesas do mundo que usam o Skype for Business, exceto algumas, escolha **Ativado exceto para domínios bloqueados**, e escolha **+** para adicionar aqueles domínios. Qualquer usuário poderá contatar você, exceto os domínios bloqueados. (Algumas empresas podem escolher essa opção, por exemplo, se estiverem em litígio e precisarem assegurar-se de que não haja contato com as outras empresas.)
    
5. Escolha **Permita que as pessoas usem o Skype for Business para se comunicar com usuários do Skype fora de sua organização**. 
    
6.  Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.
    
    Se sua organização usa outra solução para restringir os computadores em sua rede de se conectar à Internet, certifique-se de que os computadores clientes sejam capazes de acessar todos os [endereços IP e URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para conectividade Skype e pesquisa de diretório do Skype. Isso poderá exigir adicioná-las à saída lista de permissões na sua configuração de infraestrutura de firewall ou proxy.
    
7. **AGUARDE 24 HORAS PARA FAZER O TESTE**. Em qualquer momento que você alterar as configurações das comunicações externas, poderá levar até 24 horas para as alterações serem efetivadas em todos os data centers.
    
8. Mostre aos usuários como pesquisar e adicionar contatos do Skype à sua lista de contatos do Skype for Business. Oriente-os a usar a opção [Procurar por pessoas no Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Testar e solucionar problemas

Para testar sua configuração, você precisa de um contato no Skype que não seja protegido pelo firewall da empresa. Eles podem entrar no Skype usando uma conta do Gmail, do Outlook.com ou outro tipo de conta de email.
  
1. Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.
    
2. Saia do Skype for Business e entre novamente, assim você verá a opção para pesquisar o Diretório do Skype. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. No Skype for Business, pesquise seu contato no Skype e envie uma solicitação para chat. 
    
    Se você receber a mensagem, que ela não pôde ser enviada devido à política da empresa, você precisará verificar suas [configurações de firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Outra maneira de testar se o problema é o firewall é usar o wifi de um lugar que não tenha firewall, como uma cafeteria, e usar o Skype for Business para enviar uma solicitação ao contato do Skype para chat. 
    
  - **Se você enviou uma solicitação ao seu contado do Skype e ele nunca a recebeu**, peça que ele envie uma solicitação de chat para você. Se o problema for estabelecimento de conexão entre o Skype e o Skype for Business, isso geralmente resolve o problema.
    
  - Agora, se a mensagem for enviada da cafeteria, mas não de seu trabalho, então você saberá que o problema é o firewall. 
    
## <a name="what-you-can-and-cant-do"></a>O que você pode ou não fazer

- **Skype for Businessno Mac** não tem a capacidade de pesquisar e comunicar-se com contatos do Skype.
    
- Enquanto você pode pesquisar e localizar usuários Skype, eles não podem procurar e encontre Skype para usuários empresariais. Você precisa enviar-lhes uma solicitação de visita e eles precisam se conectar ao Skype e aceitá-lo, antes de você poder mensagens Instantâneas com eles. 
    
- Não é possível permitir a conectividade de mensagens instantâneas com outros provedores de mensagens instantâneas, como o Google ou Facebook. Você não pode usar o Skype for Business para enviar mensagens de texto de celular.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Quais recursos estão disponíveis ao adicionar contatos do Skype?

Contatos do Skype que entraram em sua conta da Microsoft (anteriormente Windows Live ID) podem fazer algumas, mas nem todos os recursos quando eles estão se comunicando com seu Skype para usuários comerciais.
  
|**Disponível para os contatos do Skype**|**Não disponível para os contatos do Skype**|
|:-----|:-----|
| Conversas com vídeo <br/>  Troca de mensagens instantâneas de pessoa para pessoa <br/>  Presença <br/> | Mensagens instantâneas de vários participantes <br/>  Conversas de áudio ou com vídeo com três ou mais pessoas <br/>  Compartilhamento de área de trabalho e de programas <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Tópicos relacionados

[Permitir que os usuários entrem em contato com usuários externos do Skype for Business](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
