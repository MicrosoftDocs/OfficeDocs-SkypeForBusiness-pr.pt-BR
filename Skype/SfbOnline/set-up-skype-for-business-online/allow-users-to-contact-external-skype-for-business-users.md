---
title: Permitir que os usuários entrem em contato com usuários externos do Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: 24cedb4a9fd612c3aa0c4886a9a35dd89b52fbe7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887589"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que os usuários entrem em contato com usuários externos do Skype for Business

> [!NOTE]
> Skype para federação de negócios não está disponível para o Office 365 operado pela 21Vianet e organizações do Office 365 Alemanha. 
  
Siga as etapas descritas neste artigo quando:
  
- Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.
    
- Deseja que qualquer pessoa no mundo que usa Skype for Business para conseguir encontrar e contatá-lo, usando seu endereço de email. Se as configurações padrão do Skype for Business forem usadas, isso funcionará automaticamente. Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicações entre empresas para os usuários
<a name="bk_preview"> </a>

Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) no Office 365 em ambas as organizações para fazer isso.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**
  
1. Entrar com sua conta de administração do Office 365. 
    
2. No Centro de administração do Office 365, vá para **Centros de Administração** > **Skype for Business**.
    
    ![Escolha o Centro de administração do Skype for Business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.
    
4. Para configurar a comunicação com um negócio específicos ou com usuários em outro domínio, na caixa suspensa, escolha **em somente para domínios permitidos**.
    
    OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.
    
5. Em **bloqueado ou domínios permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir.
    
6. Certificar-se de que o administrador na organização do segue essas etapas mesmas em seus **Skype para centro de administração de negócios**. Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.
    
7. Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.
    
    Se a sua organização estiver usando uma solução de firewall diferente para restringir a conexão com a Internet nos computadores da rede, verifique se seus computadores clientes podem acessar os [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) a seguir. Talvez seja necessário adicionar os FQDNs para a saída configuração da infraestrutura de lista no seu firewall ou proxy de permissões: ** \*. api.skype.com**, \* **. users.storage.live.com**e **graph.skype.com**. Para obter instruções sobre como abrir essas portas em seu firewall, consulte a documentação que o acompanha.
    
    Para obter uma lista de todas as portas que precisam ser abertas, consulte [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).

8. Certifique-se de que o administrador da organização também tiver seguido essas etapas.
    
9. **AGUARDE 24 HORAS PARA FAZER O TESTE**. Em qualquer momento que você alterar as configurações das comunicações externas, poderá levar até 24 horas para as alterações serem efetivadas em todos os data centers.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários pesquisem todas as pessoas que usam o Skype (o aplicativo gratuito!) e enviem mensagens instantâneas para elas. Para saber mais, consulte [Skype permitem que usuários corporativos adicionar contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Testar e solucionar problemas
<a name="bk_preview"> </a>

 **O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**
  
Para testar sua configuração, você precisa de um contato no Skype for Business que não seja protegido pelo firewall da empresa.
  
1. Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.
    
2. No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat.
    
    Se você receber uma mensagem que ele não pôde ser enviado devido à política da empresa, você precisará verificar novamente suas [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).
    
4. Para testar de outra maneira se o problema é o firewall, basta usar o wifi de um lugar que não tenha firewall, como uma cafeteria, e usar o Skype for Business para enviar uma solicitação ao contato do Skype para chat. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Como localizar pessoas e ser localizado ao conectar-se com outra empresa
<a name="bk_preview"> </a>

Após habilitar comunicações externas com outro Skype para usuários corporativos, os usuários podem encontrar Skype federado para usuários comerciais pesquisando por seu nome de entrada: por exemplo, Rob@contoso.com. Então, eles deverão adicionar a pessoa à lista de contatos.
  
![Para localizar um usuário em uma empresa federada, você deve procurar por seus endereços de email (Isso é geralmente também seu nome de usuário).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Dicas para configurar comunicações com empresas federadas
<a name="bk_preview"> </a>

- Para configurar a federação entre Skype para negócios 2015 e Skype para Business Online, consulte este artigo: [Configurar federação com Skype para negócios Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Para configurar a federação entre o Lync e Skype para Business Online, consulte este artigo: [Configurando o suporte de federação para um cliente Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Quando dois usuários do Skype for Business no Office 365 estão se comunicando entre si em domínios separados, eles só podem usar os recursos do Skype for Business (por exemplo, conversas por vídeo ou compartilhamento de área de trabalho) que estejam ativados em ambas as organizações.
    
- Se um Skype para usuários de negócios de sua organização é colocado em um In-loco ou retenção de litígio, qualquer conversas de mensagens Instantâneas entre esse usuário e outra Skype para usuários corporativos ou Skype serão salvo no **Itens recuperáveis** em suas caixas de correio. Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Desativar a comunicação externa para indivíduos específicos
<a name="bk_preview"> </a>

Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos.
  
1. Entrar com sua conta de administração do Office 365.
    
2. No Centro de administração do Office 365, vá para **usuários** > **usuários ativos**.
    
3. Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. No **Skype para centro de administração de negócios**, escolha **comunicações externas**.
    
    Na página **Opções** , todas as opções serão selecionadas. Desmarque a comunicações que você deseja desabilitar. A imagem a seguir mostra que Júlio poderá se comunicar com pessoas em outras empresas confiáveis, mas não com outros usuários do Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Escolha **Salvar**.
    
> [!NOTE]
> [!OBSERVAçãO] Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Tópicos relacionados
<a name="bk_preview"> </a>

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
