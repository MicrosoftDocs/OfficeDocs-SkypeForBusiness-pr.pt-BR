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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: 394613e3137c65e814cc08dd898ec797d560d1c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010934"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que os usuários entrem em contato com usuários externos do Skype for Business

> [!NOTE]
> A Federação do Skype for Business não está disponível para o Office 365 operado pela 21Vianet e pelas organizações da Alemanha do Office 365. 
  
Siga as etapas descritas neste artigo quando:
  
- Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.
    
- Você quer que qualquer outro usuário do mundo que use o Skype for Business possa encontrá-lo e contatá-lo usando o seu endereço de e-mail. Se as configurações padrão do Skype for Business forem usadas, isso funcionará automaticamente. Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicações entre empresas para os usuários
<a name="bk_preview"> </a>

Você deve ter [permissões de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) no Office 365 em ambas as organizações para fazer isso.

![Um ícone mostrando o logotipo](../images/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do teams**
  
1. Entre com sua conta de administrador do Office 365. 
    
2. No centro de administração, vá para **** > **equipes**de centros de administração.
    
    ![Escolha o administrador do teams.](../images/MS-Teams-Admin.png)
  
3. Na **central do teams**, escolha **portal** 
 ![herdado **do Skype** > escolha o portal herdado do SfB.](../images/SFBlegacy-size65.png)
 
4. No **centro de administração do Skype for Business** , escolha**comunicações externas**da **organização** > .
5. Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **Ativado somente para os domínios permitidos**.
    
    OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.
    
6. Em **domínios bloqueados ou permitidos**, **+** escolha e adicione o nome do domínio que você deseja permitir.
    
7. Verifique se o administrador da outra organização executa essas mesmas etapas no centro de **Administração do Skype for Business**. Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.
    
8. Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.
    
    Se a sua organização estiver usando uma solução de firewall diferente para restringir a conexão com a Internet nos computadores da rede, verifique se seus computadores clientes podem acessar os [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) a seguir. Isso pode exigir a adição dos FQDNs à lista de permissões de saída em seu firewall ou configuração de infraestrutura de proxy \*: ** \*. API.Skype.com**, **. Users.Storage.Live.com**e **Graph.Skype.com**. Para obter instruções sobre como abrir essas portas no firewall, consulte a documentação que a acompanha.
    
    Para obter uma lista de todas as portas que você precisa abrir, consulte [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).

9. Verifique se o administrador da organização também seguiu estas etapas.
    
10. **AGUARDE 24 HORAS PARA FAZER O TESTE**. Em qualquer momento que você alterar as configurações das comunicações externas, poderá levar até 24 horas para as alterações serem efetivadas em todos os data centers.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários pesquisem todas as pessoas que usam o Skype (o aplicativo gratuito!) e enviem mensagens instantâneas para elas. Para saber mais, confira [permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Testar e solucionar problemas
<a name="bk_preview"> </a>

 **O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**
  
Para testar sua configuração, você precisa de um contato no Skype for Business que não seja protegido pelo firewall da empresa.
  
1. Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.
    
2. No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat.
    
    Se você receber uma mensagem informando que ela não foi enviada devido à política da empresa, você precisa verificar novamente suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).
    
4. Para testar de outra maneira se o problema é o firewall, basta usar o wifi de um lugar que não tenha firewall, como uma cafeteria, e usar o Skype for Business para enviar uma solicitação ao contato do Skype para chat. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Como localizar pessoas e ser localizado ao conectar-se com outra empresa
<a name="bk_preview"> </a>

Depois de habilitar a comunicação externa com outros usuários do Skype for Business, os usuários podem encontrar usuários federados do Skype for Business procurando por seu nome de entrada: por exemplo, Rob@contoso.com. Então, eles deverão adicionar a pessoa à lista de contatos.
  
![Para localizar um usuário em uma empresa federada, você deve pesquisar seu endereço de email (geralmente, isso também é o nome do usuário).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Dicas para configurar comunicações com empresas federadas
<a name="bk_preview"> </a>

- Para configurar a Federação entre o Skype for Business 2015 e o Skype for Business Online, confira este artigo: [Configurar a Federação com o Skype for Business online](https://technet.microsoft.com/library/jj205126.aspx).
    
- Para configurar a Federação entre o Lync e o Skype for Business Online, confira este artigo: [Configurando o suporte de Federação para um cliente do Lync Online](https://technet.microsoft.com/library/hh202193.aspx).
    
- Quando dois usuários do Skype for Business no Office 365 estão se comunicando entre si em domínios separados, eles só podem usar os recursos do Skype for Business (por exemplo, conversas por vídeo ou compartilhamento de área de trabalho) que estejam ativados em ambas as organizações.
    
- Se um usuário do Skype for Business em sua organização for colocado em um local ou em uma retenção de litígio, todas as conversas de mensagens instantâneas entre esse usuário e outros usuários do Skype for Business ou do Skype serão salvas em **itens recuperáveis** na caixa de correio. Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Desativar a comunicação externa para indivíduos específicos
<a name="bk_preview"> </a>

Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos.
  
1. Entre com sua conta de administrador do Office 365.
    
2. No centro de administração, vá para usuários**ativos**do **usuários** > .
    
3. Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. No **centro de administração do Skype for Business**, escolha **comunicações externas**.
    
    Na página **Opções** , todas as opções serão selecionadas. Desmarque as comunicações que você deseja desabilitar. A imagem a seguir mostra que Júlio poderá se comunicar com pessoas em outras empresas confiáveis, mas não com outros usuários do Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Escolha **Salvar**.
    
> [!NOTE]
> [!OBSERVAçãO] Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Tópicos relacionados
<a name="bk_preview"> </a>

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
