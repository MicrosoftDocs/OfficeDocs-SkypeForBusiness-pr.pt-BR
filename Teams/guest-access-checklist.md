---
title: Lista de verificação de acesso de convidado de equipes do Microsoft
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Access de convidado equipes.
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 256ca09b8da5ccaed3ab5797e9d67246cebfee4e
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678137"
---
<a name="teams-guest-access-checklist"></a>Lista de verificação de acesso de convidado de equipes
==========================================

Use esta lista de verificação para ajudá-lo a ativar e configurar o recurso de acesso de convidado no Microsoft Teams acordo com as preferências de sua organização.




## <a name="--enable-guest-access-at-the-tenant-level"></a>Acesso de convidado Enable □ no nível de locatário

Vá para as equipes & Skype para o Centro de administração de negócios, via https://admin.teams.microsoft.com. A partir daqui, selecione 'Configurações de toda a organização' e seleciona na guia acesso do convidado por último, dentro desta guia, selecione 'Permitir acesso de convidado no Microsoft Teams' para habilitado. 

## <Need to display a photo of the new admin center>

## <a name="-enable-specific-settings-for-channels"></a>□ Habilitar configurações específicas para canais 
No aplicativo de equipes, no nível equipe individuais, configure permissões de convidado para que os convidados podem criar, atualizar e excluir canais. Além dos administradores, os proprietários de equipe podem configurar essa definição.

![Captura de tela mostra um exemplo de uma alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)


Para obter mais informações, incluindo vídeos de instruções, consulte [acesso de convidado em equipes da Microsoft](guest-access.md).



## <a name="--configure-sharing-in-office-365"></a>□ Configurar o compartilhamento no Office 365 

□ Certifique-se de que os usuários podem adicionar convidados. Veja como:

1. No Centro de administração do Office 365, vá para **configurações** > **de segurança e privacidade**.
![Captura de tela mostra um exemplo de um configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. Em **compartilhamento**, selecione **Editar**. ![Captura de tela mostra um exemplo de um botão de editar configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. Definir **permitem aos usuários adicionar novos convidados para esta organização** para **ativado**e clique em **Salvar**. ![Captura de tela mostra um exemplo de uma alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> Essa configuração equivale à configuração de **membros podem convidar** em configurações do usuário > usuários externos em Azure AD.  




## <a name="-configure-office-365-groups"></a>□ Configurar grupos de Office 365

No Centro de administração do Office 365, vá para **configurações** > **Serviços & suplementos** > **Grupos do Office 365**.

Certifique-se de **Permitir que os membros do grupo fora o conteúdo de grupo de acesso de organização** está definida como **On**. Se essa configuração estiver desativada, os convidados não conseguirá acessar nenhum conteúdo de grupo.

Certifique-se de **Permitir que os proprietários de grupo adicionar pessoas fora da organização para grupos** está definida como **On**. Se essa configuração estiver desativada, os proprietários de equipe não conseguirá adicionar novos convidados. No mínimo, essa configuração deve ser "ligado" suportar o acesso de convidado.

Para obter instruções detalhadas sobre como definir essas configurações, consulte a seção "Grupos de 365 Office" em [autorizar o acesso de convidado em equipes da Microsoft](Teams-dependencies.md) e [permitir/bloquear o acesso de convidado a grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=869658).
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>Configurar definições do □ no Azure AD para empresas (B2B)
1. Entrar no https://portal.azure.com.
2. No painel esquerdo, clique em **do Azure Active directory** .
3. Em **Gerenciar**, clique em **configurações do usuário**.
4. Em **usuários externos**, clique em **configurações de gerenciar externo de colaboração**
5. Na página **configurações de colaboração externa** , certifique-se de **que membros podem convidar** estiver definida como **Sim**. ![Captura de tela mostra um exemplo de uma alternância de configurações de AAD. ](media/guest-access-checklist-AADSettings1.png)

    

**Os membros podem convidar** ► no mínimo para dar suporte a convidados, deve ser definida como **Sim**.

> > [!NOTE]
> > Se você define **membros podem convidar** como **não** e habilita o acesso de convidado no Office 365 grupos e Teams da Microsoft, os administradores podem controlar a convites de convidado para seu diretório. Depois que os convidados estão no diretório, podem ser adicionados às equipes pelos membros não seja o administrador (proprietários da equipe).


Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).







## <a name="-verify-sharing-setting-in-sharepoint"></a>Configuração de compartilhamento □ Verify no SharePoint
1. Entre no Centro de Administração do Office 365.
2. Clique em **Administração Central**e selecione **SharePoint**.
3. No Centro de administração do SharePoint, selecione **compartilhamento**.
4. Verifique se a opção para **não permitir o compartilhamento fora da sua organização** *não* está selecionado. ![Captura de tela mostra um exemplo de uma alternância de configurações de Sparepoint Online. ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>Tipos e licenças de conta Verify □

- **Conta licenciada para equipes**: para uma conta de "Convidado" como raiz com uma conta de usuário real em alguns outro locatário do Office 365, essa conta de usuário real deve ser licenciada para equipes para "Convidado". 
- **Conta deve ser escola do Office 365 ou trabalhar conta, ou conta MSA**: atualmente, os usuários que têm um endereço de email correspondente a um Windows Azure Active Directory, trabalho do Office 365 ou conta escola ou uma conta da Microsoft (MSA) podem ser adicionados como um usuário convidado. 
 
## <a name="-configure-environment"></a>Ambiente de Configure □


Convidados que são necessárias para usar a autenticação multifator (MFA), se for necessário para o inquilino de hospedagem.
Para obter mais detalhes, consulte [modelos de identidade e autenticação no equipes da Microsoft](identify-models-authentication.md).

## <a name="-understand-limitations-for-guests"></a>Limitações de Noções básicas sobre □ para convidados

A experiência de convidado tem limitações por design. Verifique se que você compreende a experiência de convidado, então você não tenta corrigir algo que não é um problema.
Por exemplo, aqui está uma lista de alguns da funcionalidade que não está disponível para um convidado em Teams da Microsoft:

- OneDrive for Business
- Pesquisa de pessoas fora de equipes
- Calendário, reuniões agendadas ou detalhes da reunião
- PSTN
- Organograma
- Criar ou revisar uma equipe
- Navegar para uma equipe
- Carregar arquivos para um bate-papo entre duas pessoas

Para obter mais detalhes, consulte [o que a experiência de convidado é como](guest-experience.md) e [acesso de convidado em grupos do Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).




## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas com a adição de convidados no Teams da Microsoft, consulte o [Guia de solução de problemas de acesso de convidado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


