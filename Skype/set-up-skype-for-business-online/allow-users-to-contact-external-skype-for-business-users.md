---
title: "Permitir que os usuários entrem em contato com usuários externos do Skype for Business"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
- Adm_UI_Elements
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94

description: "See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. "
---

# Permitir que os usuários entrem em contato com usuários externos do Skype for Business

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
> [!NOTE]
> Skype para a federação de negócios não está disponível para o Office 365 operado pela 21Vianet e organizações de Alemanha do Office 365. 
  
Siga as etapas descritas neste artigo quando: 
  
- Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.
    
- OU, você deseja que todas as pessoas que estiverem usando o Skype for Business possam localizar e contatar você, usando seu endereço de email. Se as configurações padrão do Skype for Business forem usadas, isso funcionará automaticamente. Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.
    
## Habilitar comunicações entre empresas para os usuários
<a name="bk_preview"> </a>

Você deve ter [Tudo sobre as funções de administrador do Office 365](about-office-365-admin-roles.md) no Office 365 para fazer isso.
  
1. Entrar com sua conta de administrador Office 365.
    
2. No Centro de administração do Office 365, vá para **Centros de Administração** > **Skype for Business**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. No **Centro de administração do Skype for Business**, escolha **organização** > **comunicações externas**.
    
4. Para configurar a comunicação com um negócio específico ou com usuários em outro domínio, na caixa suspensa, escolha **ativado apenas para domínios permitidos**.
    
    OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.
    
5. Em **domínios permitidos ou bloqueados**, escolha **+** e adicione o nome do domínio que você deseja permitir.
    
6. Certificar-se de que o administrador da organização outros faz essas mesmas etapas em seus **Centro de administração do Skype for Business**. Por exemplo, na lista de **domínios permitidos**, administrador precisa digite o domínio da sua empresa.
    
7. Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente. 
    
    Se sua organização estiver usando uma solução de firewall diferente para restringir o acesso de computadores na rede de conexão com a Internet, certifique-se de que os computadores cliente são capazes de acessar os seguintes [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Talvez seja necessário adicionar os FQDNs em saída permitem lista no seu firewall ou proxy configuração de infraestrutura: ***. api.skype.com, *. users.storage.live.com e graph.skype.com**. Para obter instruções sobre como abrir essas portas no firewall, verifique a documentação que veio com ele.
    
    Para obter uma lista de todas as portas que você precisa abrir, consulte [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo) no artigo[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
    
8. **ESPERAR até 24 horas para testar**. Sempre que você altera as configurações de comunicações externas, pode levar até 24 horas para que as alterações popular entre todos os centros de dados.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários para pesquisa e mensagens Instantâneas com todos que usam o Skype, o aplicativo gratuito consumidor! Para saber mais, consulte[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## Testar e solucionar problemas
<a name="bk_preview"> </a>

 **O problema mais comum que as pessoas enfrentam diariamente ao configurar a comunicação para empresas está recebendo suas [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) à direita.**
  
Para testar sua instalação, você precisa de um contato em Skype for Business que não esteja por trás do firewall da empresa.
  
1. Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.
    
2. No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat. 
    
    Se você receber uma mensagem que ele não pôde ser enviado devido a política da empresa, você precisa doublecheck suas [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
    
3. Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas). 
    
4. Outra maneira de testar se o problema é seu firewall é ir para um local de wifi não atrás do firewall como uma cafeteria e usar Skype for Business para enviar uma solicitação para seu contato para bate-papo. Se a mensagem percorre lá, mas não quando você estiver no trabalho, você conhece o problema é seu firewall.
    
## Como localizar pessoas e ser localizado ao conectar-se com outra empresa
<a name="bk_preview"> </a>

Depois de habilitar comunicações externas com outros usuários de Skype for Business, seus usuários possam encontrá usuários federados Skype for Business procurando por seu nome de entrada: por exemplo, Rob@contoso.com. Em seguida, eles precisam adicionar a pessoa à sua lista de contatos.
  
![To find a user in a federated business, you must search for their email address (this is usally also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## Dicas para configurar comunicações com empresas federadas
<a name="bk_preview"> </a>

- Para configurar a federação entre o Skype for Business 2015 e o Skype for Business Online, veja este artigo do TechNet: [Configurar federação com o Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Para configurar a federação entre o Lync e o Skype for Business Online, veja este artigo do TechNet: [Configurando o suporte de federação para um cliente do Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Quando dois usuários do Skype for Business no Office 365 estão se comunicando entre si em domínios separados, eles só podem usar os recursos do Skype for Business (por exemplo, conversas por vídeo ou compartilhamento de área de trabalho) que estejam ativados em ambas as organizações. 
    
- Se um usuário Skype for Business em sua organização for colocado em um local ou litígio, qualquer conversas de mensagem Instantânea entre esse usuário e outras Skype for Business ou usuários do Skype serão salvos em **Itens recuperáveis** em suas caixas de correio. Essas conversas não são salvas na pasta **Histórico de conversas** em suas caixas de correio.
    
## Desativar a comunicação externa para indivíduos específicos
<a name="bk_preview"> </a>

Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos. 
  
1. Entrar com sua conta de administrador Office 365.
    
2. No Centro de administração do Office 365, vá para **usuários** > **usuários ativos**.
    
3. Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Do **Skype para o Centro de administração de negócios**, escolha **comunicações externas**.
    
    Na página **Opções**, todas as opções serão selecionadas. Desmarque as comunicações que você deseja desativar. A imagem a seguir mostra que Jakob será capaz de se comunicar com as pessoas de outras empresas confiáveis, mas não com outros usuários do Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Escolha **Salvar**.
    
> [!NOTE]
> Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor. 
  
## 
<a name="bk_preview"> </a>

 *Última atualização do artigo: 23 de março de 2017* 
  
## 
<a name="bk_preview"> </a>

||
|:-----|
|![O ícone pequeno do LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Novo no Office 365?**         Descubra cursos de vídeo gratuitos para **Administradores do Office 365 e profissionais de TI**, disponibilizados pelo LinkedIn Learning. |
   
## Tópicos Relacionados
<a name="bk_preview"> </a>

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

