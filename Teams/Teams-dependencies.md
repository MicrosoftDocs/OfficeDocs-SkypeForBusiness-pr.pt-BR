---
title: Autorizar acesso de convidados no Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/18
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Gerenciar recursos e funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: be1aa39a73cf5c4a28866ac8b702afebeb992b0d
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753815"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorizar acesso de convidados no Microsoft Teams
===========================================

Para atender às exigências de sua organização, você pode gerenciar os recursos e as funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização. Todos os níveis de autorização são aplicáveis ao seu locatário do Office 365. Cada nível de autorização controla a experiência do convidado conforme mostrado a seguir:

- **Azure Active Directory**: O acesso de convidados no Microsoft Teams usa a plataforma B2B (entre empresas) do Azure AD. Controla a experiência dos convidados no nível de diretório, locatário e aplicativo. 
- **Microsoft Teams**: Controla somente o Microsoft Teams. 
- **Grupos do Office 365**: Controla a experiência dos convidados nos Grupos do Office 365 e no Microsoft Teams.
- **SharePoint Online e OneDrive for Business**: Controla a experiência dos convidados no SharePoint Online, no OneDrive for Business, nos Grupos do Office 365 e no Microsoft Teams.

Esses níveis diferentes de autorização fornecem flexibilidade para a forma como você configura o acesso de convidados para sua organização. Por exemplo, se você não quiser permitir usuários convidados em seu Teams da Microsoft, mas quer permitir que geral em sua organização, apenas desative o acesso de convidado no Microsoft Teams. Outro exemplo: Você pode habilitar o acesso de convidados no AAD, no Microsoft Teams e nos Grupos do Office 365, mas depois desabilitar a adição de usuários convidados em equipes selecionadas que correspondam a um ou mais critérios, como classificação de dados correspondente à confidencial. O SharePoint Online e o OneDrive for Business têm suas próprias configurações de acesso de convidados que não dependem dos Grupos do Office 365. 

> [!NOTE]
> Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

O diagrama a seguir mostra como a dependência de autorização de acesso de convidados é concedida e integrada entre o Azure Active Directory, o Microsoft Teams e o Office 365.

![Diagrama de dependências de autorização para acesso de convidados.](media/teams_dependencies_image1.png)

O próximo diagrama mostra, em um alto nível, como a experiência do usuário funciona com o modelo de permissão por meio de um fluxo de convite e resgate de acesso do convidado típica.

![Diagrama de fluxos de convite e resgate](media/authorize-guest-image1.png)

É importante observar aqui que conectores, bots e aplicativos podem exigir seu próprio conjunto de permissões e/ou concorda específicos à conta de usuário. Essas talvez precisem ser concedidas separadamente. Da mesma forma, o SharePoint pode impor limites compartilhamento extra externos para um usuário específico, grupos de usuários ou até mesmo no nível do site.

## <a name="control-guest-access-in-azure-active-directory"></a>Controlar o acesso de convidado no Windows Azure Active Directory

Use o Azure AD para determinar se os colaboradores externos podem ser convidados para seu locatário como convidados e de que forma. Para obter mais informações sobre o acesso de convidado B2B do Azure, consulte [o que é o acesso de usuário convidado no Windows Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b). Para obter informações sobre funções do Azure AD, consulte [conceder permissões aos usuários de organizações parceiras no seu locatário do Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role).

As configurações de convites são aplicáveis no nível do locatário e controlam a experiência dos convidados no nível de diretório, locatário e aplicativo. 

![Captura de tela das Configurações do usuário no portal do Azure Active Directory.](media/teams_dependencies_image2.png)

Azure AD inclui as configurações a seguir para configurar usuários externos:

- **Permissões de usuário convidado estão limitadas**: **Sim** , significa que os convidados não têm permissão para determinadas tarefas de diretório, como enumerar os usuários, grupos ou outros recursos de diretório. Além disso, os convidados não podem ser atribuídos às funções administrativas em seu diretório. **Não** significa que os clientes por ter o mesmo acesso aos dados de diretório que usuários regulares tem em seu diretório.
- **Administradores e usuários à função do autor do convite convidado podem convidar**: **Sim** , significa que a administradores e usuários à função de "Convidado quem convida" será capazes de convidar as pessoas para o inquilino. **Não** significa que os administradores e os usuários não podem convidar as pessoas para o inquilino.
- **Os membros podem convidar**: **Sim** , significa que não seja o administrador membros de seu diretório podem convidar as pessoas para colaborar nos recursos protegidos por sua Azure AD, como sites do SharePoint ou recursos do Windows Azure. **Não** significa que somente os administradores podem convidar clientes por ao seu diretório.</br>
      
    > [!NOTE]
    > Atualmente, equipes não tem suporte para a função do autor do convite convidado. no mínimo os **membros podem convidar** alternância deve ser definida como **Sim** para acesso de convidado para trabalhar em equipes.
- **Convidados podem convidar**: **Sim** significa que convidados em seu diretório, sozinhos, podem convidar outros convidados para colaborar nos recursos protegidos por sua Azure AD, como sites do SharePoint ou recursos do Windows Azure. **Não** significa que os clientes por não pode convidar outros convidados para colaborar com sua organização.
 
Para obter mais informações sobre como controlar quem pode convidar pessoas, consulte [convites de representante para colaboração do Windows Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)

> [!NOTE]
> Também é possível gerenciar quais domínios podem ser convidados para seu locatário como convidados. Consulte [permitir/bloquear o acesso de convidado a grupos do Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups). 

Adicionando a conta do usuário convidado manualmente para o Windows Azure AD B2B não é necessário, pois a conta será adicionada ao diretório automaticamente quando você adiciona o convidado para equipes. 

Licenciamento do Azure AD permite que você adicione até 5 convidados por licença. Para obter mais informações sobre o licenciamento do Azure AD, consulte [diretrizes de licenciamento de colaboração do Windows Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="control-guest-access-in-teams"></a>Controlar o acesso de convidado em equipes

Em equipes, você pode controlar se a experiência de convidado está habilitada ou desabilitada para sua organização. A configuração está desabilitada por padrão e aplica no nível do locatário para equipes apenas.

Você pode gerenciar as configurações de acesso de convidado equipes do Centro de administração do Microsoft Teams. Para obter mais detalhes, consulte [Habilitar ou desabilitar o acesso de convidados no Microsoft Teams](set-up-guests.md). 


## <a name="control-guest-access-in-office-365-groups"></a>Controlar o acesso de convidado em grupos do Office 365

Nos Grupos do Office 365, você pode controlar a adição de usuários convidados e o acesso de convidados a todos os grupos do Office 365 e ao Microsoft Teams em sua organização.

1. Entre usando sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.
    
3. Selecione **Grupos do Office 365**.
    
     ![Grupos do Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  
4. Na página grupos do Office 365, defina a alternância para **ou **desativado**,** dependendo se você deseja permitir que os proprietários equipe e agrupar fora de seus grupos de acesso para Office 365 da organização. Clique ou toque no botão de alternância para **Habilitar** ao lado de **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**. Se você ativar esta alternância para **ativado**, você verá outra opção para controlar se você quiser permitir que o grupo de proprietários de equipe adicionar pessoas fora da sua organização para grupos do Office 365 e equipes da Microsoft. Defina este alternância para **ativado** , se você quiser permitir que o grupo e os proprietários de equipe adicionar usuários convidados. 
 
   ![A captura de tela mostra o painel de Grupos do Office 365 com as opções habilitadas para permitir que membros de grupo de fora da organização acessem o conteúdo do grupo e para permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)

Essas configurações se aplicam a nível de locatário e controlam a experiência de convidado no Office 365 grupos e Teams da Microsoft.

Consulte [Convidado acessar de grupos do Office 365](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) para obter mais informações sobre o acesso de convidado em grupos, incluindo como funciona o acesso de convidado, como gerenciar o acesso do convidado e respostas para perguntas frequentes.

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>Acesso de convidado de controle para o SharePoint Online e o OneDrive for Business

O Teams depende do SharePoint Online e do OneDrive for Business para armazenar arquivos e documentos para canais e conversas de bate-papo.  
   
Para habilitar a experiência completa de acesso de convidados no Teams, os administradores do Office 365 precisam selecionar **Habilitar** nas seguintes configurações:

- No SharePoint Online: **Permitir apenas compartilhamento com usuários externos já constantes do diretório**
    
    Para obter mais informações, consulte [Gerenciar compartilhamento externo para o seu ambiente do SharePoint Online](https://docs.microsoft.com/sharepoint/external-sharing-overview).
    
- Nos grupos do Office 365: **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**
    
    Para obter mais informações, consulte [controlar o acesso de convidado em grupos do Office 365](#control-guest-access-in-office-365-groups), acima.
  
Essas configurações se aplicam a nível de locatário e controlam a experiência de convidado no SharePoint Online, o OneDrive for Business, equipes e grupos do Office 365.

Você pode gerenciar as configurações de usuário externo do SharePoint Online para o site de equipe conectado ao Teams. Para obter mais detalhes, veja [Gerenciar as configurações do site da sua equipe do SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).

## <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado versus acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]