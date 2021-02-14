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
description: 'Veja como configurar o Skype for Business para permitir que os usuários conversem com usuários em outra organização ou permitir que contatos externos conversem com eles. '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625047"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que os usuários entrem em contato com usuários externos do Skype for Business
  
Siga as etapas descritas neste artigo quando:
  
- Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.

- Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.

- Você quer que qualquer outra pessoa no mundo que use o Skype for Business possa encontrá-lo e contatá-lo usando seu endereço de email. Se você e eles usarem as configurações padrão do Skype for Business, isso funcionará automaticamente. Caso não o faça, é necessário garantir que a configuração não está bloqueando seu domínio.

## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicações entre empresas para os usuários

<a name="bk_preview"> </a>

Você deve ter [permissões de](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) administrador no Microsoft 365 ou no Office 365 em ambas as organizações para fazer essa comunicação.

![Um ícone mostrando o logotipo do Microsoft Teams ](../images/teams-logo-30x30.png) **usando o centro de administração do Teams**
  
1. Entre com sua conta de administrador do Microsoft 365 ou do Office 365.

2. No centro de administração, vá para **Equipes de Centros de**  >  **Administração.**

    ![Escolha o Administrador do Teams.](../images/MS-Teams-Admin.png)
  
3. No Centro **do Teams,** escolha Portal Herdado do **Skype** Escolha o >  
  ![ Portal Herdado do SfB.](../images/SFBlegacy-size65.png)

4. No **Centro de administração Skype for Business**, escolha **Organização** > **Comunicações externas**.
5. Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **Ativado somente para os domínios permitidos**.

    OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.

6. Em **Domínios bloqueados ou permitidos,** escolha e adicione o nome do **+** domínio que você deseja permitir.

7. Certifique-se de que o administrador de outra organização faça as mesmas etapas no centro **de administração do Skype for Business.** Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.

8. Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.

    Se a sua organização estiver usando uma solução de firewall diferente para restringir a conexão com a Internet nos computadores da rede, verifique se seus computadores clientes podem acessar os [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) a seguir. Isso pode exigir a adição de FQDNs à lista de permitir saída na configuração de infraestrutura de proxy ou firewall: **\* .api.skype.com,** \* **.users.storage.live.com** e **graph.skype.com.** Para obter instruções sobre como abrir essas portas no firewall, verifique a documentação que veio com ela.

    Para ver uma lista de todas as portas que você precisa abrir, consulte [URLs do Office 365 e intervalos de endereços IP.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)

9. Certifique-se de que o administrador da organização também tenha seguido essas etapas.

10. **AGUARDE 24 HORAS PARA FAZER O TESTE**. Quando você altera as configurações de comunicações externas, pode levar até 24 horas para que as alterações se preencham em todos os data centers.

![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários pesquisem todas as pessoas que usam o Skype (o aplicativo gratuito!) e enviem mensagens instantâneas para elas. Para saber mais, consulte [Permitir que os usuários do Skype for Business adicionem contatos do Skype.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>Testar e solucionar problemas

<a name="bk_preview"> </a>

 **O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**
  
Para testar sua configuração, você precisa de um contato no Skype for Business que não seja protegido pelo firewall da empresa.
  
1. Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.

2. No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat.

    Se você receber uma mensagem de que ela não pôde ser enviada devido à política da empresa, será necessário verificar duas vezes suas URLs e intervalos de endereços IP do [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)

3. Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).

4. Outra maneira de testar se o problema é o firewall é ir para um local wifi e não atrás do firewall, como um café. Use o Skype for Business para enviar uma solicitação ao seu contato para conversar. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Como localizar pessoas e ser localizado ao conectar-se com outra empresa

<a name="bk_preview"> </a>

Depois que você habilitar a comunicação externa com outros usuários do Skype for Business, os usuários poderão encontrar usuários federados do Skype for Business pesquisando seus nomes de conexão. Um exemplo é Rob@contoso.com. Então, eles deverão adicionar a pessoa à lista de contatos.
  
![Para encontrar um usuário em uma empresa federada, você deve procurar seu endereço de email (geralmente também é o nome de sua assinatura).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Dicas para configurar comunicações com empresas federadas

<a name="bk_preview"> </a>

- Para configurar a federação entre o Skype for Business 2015 e o Skype for Business Online, confira este artigo: Configurar a [federação com o Skype for Business Online.](https://technet.microsoft.com/library/jj205126.aspx)

- Para configurar a federação entre o Lync e o Skype for Business Online, confira este artigo: Configurando o Suporte de Federação [para um cliente do Lync Online.](https://technet.microsoft.com/library/hh202193.aspx)

- Quando dois usuários do Skype for Business no Microsoft 365 ou no Office 365 estão se comunicando entre si em domínios separados, eles só podem usar recursos do Skype for Business (por exemplo, conversas com vídeo ou compartilhamento de área de trabalho) que estão ativos em ambas as organizações.

- Se um usuário do Skype for Business em sua organização for colocado em uma In-Place ou Em Espera de Litígio,  qualquer conversa por mensagem de email entre esse usuário e outros usuários do Skype for Business ou do Skype será salva em Itens Recuperáveis em sua caixa de correio. Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Desativar a comunicação externa para indivíduos específicos

<a name="bk_preview"> </a>

Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos.
  
1. Entre com sua conta de administrador do Microsoft 365 ou do Office 365.

2. No centro de administração, vá para **Usuários**  >  **Ativos.**

3. Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. No Centro **de administração do Skype for Business,** escolha **Comunicações externas.**

    Na página **Opções,** todas as opções serão selecionadas. Limpe as comunicações que você deseja desabilitar. A imagem a seguir mostra que Júlio poderá se comunicar com pessoas em outras empresas confiáveis, mas não com outros usuários do Skype.

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Escolha **Salvar**.

> [!NOTE]
> [!OBSERVAçãO] Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Tópicos relacionados

<a name="bk_preview"> </a>

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
  