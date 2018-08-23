---
title: Autorizar acesso de convidados no Microsoft Teams
author: lolaj
ms.author: sbhatta
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Gerenciar recursos e funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7a1fb7ce7910963cf7b665c2e0e26788f9487ca
ms.sourcegitcommit: 5943c41bac520558733d08f4a9ecc4425c422ff9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2018
ms.locfileid: "22599348"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorizar acesso de convidados no Microsoft Teams
===========================================

Para atender às exigências de sua organização, você pode gerenciar os recursos e as funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização. Todos os níveis de autorização são aplicáveis ao seu locatário do Office 365. Cada nível de autorização controla a experiência do convidado conforme mostrado a seguir:
- **Azure Active Directory**: O acesso de convidados no Microsoft Teams usa a plataforma B2B (entre empresas) do Azure AD. Controla a experiência dos convidados no nível de diretório, locatário e aplicativo. 
- **Microsoft Teams**: Controla somente o Microsoft Teams. 
- **Grupos do Office 365**: Controla a experiência dos convidados nos Grupos do Office 365 e no Microsoft Teams.
- **SharePoint Online e OneDrive for Business**: Controla a experiência dos convidados no SharePoint Online, no OneDrive for Business, nos Grupos do Office 365 e no Microsoft Teams.

Esses níveis diferentes de autorização fornecem flexibilidade para a forma como você configura o acesso de convidados para sua organização. Por exemplo, se você não deseja permitir usuários convidados em sua organização do Microsoft Teams, basta desativar o acesso de convidados no aplicativo. Outro exemplo: Você pode habilitar o acesso de convidados no AAD, no Microsoft Teams e nos Grupos do Office 365, mas depois desabilitar a adição de usuários convidados em equipes selecionadas que correspondam a um ou mais critérios, como classificação de dados correspondente à confidencial. E, talvez, você não use os Grupos do Office 365. O SharePoint Online e o OneDrive for Business têm suas próprias configurações de acesso de convidados que não dependem dos Grupos do Office 365. 

> [!NOTE]
> Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

  O diagrama a seguir mostra como a dependência de autorização de acesso de convidados é concedida e integrada entre o Azure Active Directory, o Microsoft Teams e o Office 365.


![Diagrama de dependências de autorização para acesso de convidados.](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a>Azure Active Directory

Com a colaboração B2B do Azure AD, o envio de convites para usuários convidados potenciais não é restrito aos administradores de locatários. Em vez disso, você pode usar políticas para delegar o envio de convites a usuários cujas funções permitem o envio de convites.

As configurações de convites são aplicáveis no nível do locatário e controlam a experiência dos convidados no nível de diretório, locatário e aplicativo. No mínimo para dar suporte a convidados, **os membros podem convidar** deve ser definida como **Sim**.


![Captura de tela das Configurações do usuário no portal do Azure Active Directory.](media/teams_dependencies_image2.png)

Azure AD inclui as configurações a seguir para configurar usuários externos:
- **Permissões de usuário convidado estão limitadas**: **Sim** , significa que os convidados não têm permissão para determinadas tarefas de diretório, como enumerar os usuários, grupos ou outros recursos de diretório. Além disso, os convidados não podem ser atribuídos às funções administrativas em seu diretório. **Não** significa que os clientes por ter o mesmo acesso aos dados de diretório que usuários regulares tem em seu diretório.
- **Administradores e usuários à função do autor do convite convidado podem convidar**: **Sim** , significa que a administradores e usuários à função de "Convidado quem convida" será capazes de convidar as pessoas para o inquilino. **Não** significa que os administradores e os usuários não podem convidar as pessoas para o inquilino.
- **Os membros podem convidar**: **Sim** , significa que não seja o administrador membros de seu diretório podem convidar as pessoas para colaborar nos recursos protegidos por sua Azure AD, como sites do SharePoint ou recursos do Windows Azure. **Não** significa que somente os administradores podem convidar clientes por ao seu diretório.
- **Convidados podem convidar**: **Sim** significa que convidados em seu diretório, sozinhos, podem convidar outro convidado para colaborar nos recursos protegidos por sua Azure AD, como sites do SharePoint ou recursos do Windows Azure. **Não** significa que os clientes por não pode convidar outros convidados para colaborar com sua organização.
 


> [!NOTE]
> Também é possível gerenciar quais domínios podem ser convidados para seu locatário como convidados. Consulte [permitir/bloquear o acesso de convidado a grupos do Office 365](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups). 

## <a name="microsoft-teams"></a>Microsoft Teams
No Microsoft Teams, você pode controlar se a experiência do convidado será habilitada ou desabilitada para a sua organização. A configuração é desabilitada por padrão e é aplicável no nível do locatário somente no Microsoft Teams.



Você pode gerenciar as configurações de acesso de convidados do Microsoft Teams no Centro de administração do Office 365. Para obter mais detalhes, consulte [Habilitar ou desabilitar o acesso de convidados no Microsoft Teams](set-up-guests.md). 


## <a name="office-365-groups"></a>Grupos do Office 365

Nos Grupos do Office 365, você pode controlar a adição de usuários convidados e o acesso de convidados a todos os grupos do Office 365 e ao Microsoft Teams em sua organização.

1. Entre usando sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.
    
  
3. Selecione **Grupos do Office 365**.
    
     ![Grupos do Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. Na página de grupos do Office 365, selecione o botão de alternância para **Habilitar** ou **Desabilitar**, dependendo se desejar permitir que os proprietários de equipes e de grupos de fora de sua organização acessem os grupos do Office 365. Clique ou toque no botão de alternância para **Habilitar** ao lado de **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**. Se você definir este botão de alternância como Ativar, verá outra opção para permitir ou não que os proprietários de grupos e equipes adicionem pessoas fora de sua organização aos Grupos do Office 365 e ao Microsoft Teams. Defina este botão de alternância como Ativar, se você deseja permitir que proprietários de grupos e equipes adicionem usuários convidados. ![A captura de tela mostra o painel de Grupos do Office 365 com as opções habilitadas para permitir que membros de grupo de fora da organização acessem o conteúdo do grupo e para permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




As configurações anteriores são aplicáveis no nível de locatário e controlam a experiência dos convidados nos Grupos do Office 365 e no Microsoft Teams.


## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online e OneDrive for Business

O Teams depende do SharePoint Online e do OneDrive for Business para armazenar arquivos e documentos para canais e conversas de bate-papo.  
  
    
    
Para habilitar a experiência completa de acesso de convidados no Teams, os administradores do Office 365 precisam selecionar **Habilitar** nas seguintes configurações:
  
    
    

- No SharePoint Online: **Permitir apenas compartilhamento com usuários externos já constantes do diretório**
    
    Para obter mais informações, consulte [Gerenciar compartilhamento externo para o seu ambiente do SharePoint Online](https://docs.microsoft.com/en-us/sharepoint/external-sharing-overview).
    
  
- Nos grupos do Office 365: **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**
    
    Para obter mais informações, consulte [Controle do acesso de convidados no Microsoft Teams](#controlguest).
  

As configurações anteriores são aplicáveis no nível de locatário e controlam a experiência dos convidados no SharePoint Online, no OneDrive for Business, nos Grupos do Office 365 e no Microsoft Teams.


Você pode gerenciar as configurações de usuário externo do SharePoint Online para o site de equipe conectado ao Teams. Para obter mais detalhes, veja [Gerenciar as configurações do site da sua equipe do SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).
