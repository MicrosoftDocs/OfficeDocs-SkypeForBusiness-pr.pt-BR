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
ms.localizationpriority: medium
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
ms.openlocfilehash: e98f30718bb44a3ca2e5f48560d7f38552a2ef49
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731110"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Permitir que os usuários entrem em contato com usuários externos do Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
Siga as etapas descritas neste artigo quando:
  
- Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.

- Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.

- Você deseja que qualquer outra pessoa no mundo que usa Skype for Business possa encontrar e entrar em contato com você usando seu endereço de email. Se as configurações padrão do Skype for Business forem usadas, isso funcionará automaticamente. Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.

## <a name="enable-business-to-business-communications-for-your-users"></a>Habilitar comunicações entre empresas para os usuários

<a name="bk_preview"> </a>

Você deve ter [permissões de](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) administrador em Microsoft 365 ou Office 365 em ambas as organizações para fazer essa comunicação.

![Um ícone mostrando o logotipo Microsoft Teams.](../images/teams-logo-30x30.png) **Usando o Teams de administração**
  
1. Entre com sua conta Microsoft 365 ou Office 365 administrador.

2. No centro de administração, vá para **Centros de Administração**  >  **Teams**.

    ![Escolha o Teams Administrador.](../images/MS-Teams-Admin.png)
  
3. No centro **Teams,** escolha **Skype** > **Portal Herdado** 
  ![ Escolha o Portal Herdado do SfB.](../images/SFBlegacy-size65.png)

4. No **Centro de administração Skype for Business**, escolha **Organização** > **Comunicações externas**.
5. Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **Ativado somente para os domínios permitidos**.

    OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.

6. Em **Domínios bloqueados ou permitidos,** escolha e adicione o **+** nome do domínio que você deseja permitir.

7. Certifique-se de que o administrador da outra organização faça essas mesmas etapas em seu **Skype for Business de administração.** Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.

8. Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.

    Se a sua organização estiver usando uma solução de firewall diferente para restringir a conexão com a Internet nos computadores da rede, verifique se seus computadores clientes podem acessar os [URLs e intervalos de endereços IP do Office 365](/microsoftteams/office-365-urls-ip-address-ranges) a seguir. Isso pode exigir a adição de FQDNs à lista de autorizações de saída em sua configuração de infraestrutura de firewall ou proxy: **\* .api.skype.com,** \* *_.users.storage.live.com_* e **graph.skype.com**. Para obter instruções sobre como abrir essas portas no firewall, verifique a documentação que veio com ela.

    Para uma lista de todas as portas que você precisa abrir, consulte [Office 365 URLs e intervalos de endereços IP.](/microsoftteams/office-365-urls-ip-address-ranges)

9. Certifique-se de que o administrador na organização também tenha seguido estas etapas.

10. **AGUARDE 24 HORAS PARA FAZER O TESTE**. Quando você altera as configurações de comunicações externas, pode levar até 24 horas para que as alterações se preencham em todos os data centers.

![Skype.](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários pesquisem e IM com todos que usam Skype, o aplicativo de consumidor livre! Para saber mais, consulte [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Testar e solucionar problemas

<a name="bk_preview"> </a>

 **O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**
  
Para testar sua configuração, você precisa de um contato no Skype for Business que não seja protegido pelo firewall da empresa.
  
1. Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.

2. No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat.

    Se você receber uma mensagem de que ela não pôde ser enviada devido à política da empresa, você precisará verificar duas vezes suas URLs de Office 365 e [intervalos de endereços IP.](/microsoftteams/office-365-urls-ip-address-ranges)

3. Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).

4. Outra maneira de testar se o problema é o firewall é ir para um local wifi não atrás do firewall, como uma cafeteria. Use Skype for Business para enviar uma solicitação ao seu contato para chat. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Como localizar pessoas e ser localizado ao conectar-se com outra empresa

<a name="bk_preview"> </a>

Depois de habilitar a comunicação externa com outros usuários Skype for Business, os usuários poderão encontrar usuários federados Skype for Business pesquisando seus nomes de login. Um exemplo é Rob@contoso.com. Então, eles deverão adicionar a pessoa à lista de contatos.
  
![Para encontrar um usuário em uma empresa federada, você deve pesquisar seu endereço de email (geralmente também é o nome de login).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Dicas para configurar comunicações com empresas federadas

<a name="bk_preview"> </a>

- Para configurar a federação entre Skype for Business 2015 e Skype for Business Online, consulte este artigo: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).

- Para configurar a federação entre o Lync e Skype for Business Online, consulte este artigo: Configurando o Suporte de Federação [para um cliente do Lync Online.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)

- Quando dois Skype for Business usuários no Microsoft 365 ou Office 365 estão se comunicando uns com os outros em domínios separados, eles só podem usar recursos Skype for Business (por exemplo, conversas de vídeo ou compartilhamento de área de trabalho) que são ativos em ambas as organizações.

- Se um usuário Skype for Business em sua organização for colocado em uma In-Place ou Responsabilidade de Litígio, quaisquer conversas de mensagens de  IM entre esse usuário e outros usuários Skype for Business ou Skype serão salvas em Itens Recuperáveis em suas caixas de correio. Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Desativar a comunicação externa para indivíduos específicos

<a name="bk_preview"> </a>

Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos.
  
1. Entre com sua conta Microsoft 365 ou Office 365 administrador.

2. No centro de administração, vá para **Usuários**  >  **Usuários ativos**.

3. Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.

    ![Escolha Skype for Business.](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. No centro **Skype for Business de administração,** escolha **Comunicações externas**.

    Na página **Opções,** todas as opções serão selecionadas. Limpe as comunicações que você deseja desabilitar. A imagem a seguir mostra que Júlio poderá se comunicar com pessoas em outras empresas confiáveis, mas não com outros usuários do Skype.

    ![Escolha Contatos externos.](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Escolha **Salvar**.

> [!NOTE]
> [!OBSERVAçãO] Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Tópicos relacionados

<a name="bk_preview"> </a>

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
