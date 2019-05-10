---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0273a9b6c308d8d53fdb640bac6787568398c5be
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865094"
---
<a name="teams-guest-access-checklist"></a>Lista de verificação de acesso de convidado equipes
==========================================

Use esta lista de verificação para ajudá-lo a ativar e configurar o recurso de acesso de convidado no Microsoft Teams acordo com as preferências de sua organização.

## <a name="understand-the-limitations-for-guests"></a>Compreender as limitações de convidados

A experiência de convidado tem limitações por design. Verifique se que você compreende a experiência de convidado, então você não tenta corrigir algo que não é um problema. Por exemplo, aqui está uma lista de alguns da funcionalidade que não está disponível para um convidado em Teams da Microsoft:

- OneDrive for Business
- Pesquisa de pessoas fora de equipes
- Calendário, reuniões agendadas ou detalhes da reunião
- PSTN
- Organograma
- Criar ou revisar uma equipe
- Navegar para uma equipe
- Carregar arquivos para um bate-papo entre duas pessoas

Para obter mais detalhes, consulte [o que a experiência de convidado é como](guest-experience.md) e [acesso de convidado em grupos do Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

### <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado vs. acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Se seus convidados estão vendo erros de licença

Acesso de convidado no Microsoft Teams usa o Azure Active Directory corporativos para negócios (B2B) e seu modelo de licenciamento. Se você está vendo a erros de licenciamento, certifique-se ler as orientações de licenciamento B2B para entender os requisitos de licenciamento que sua organização tem para que os usuários sejam capazes de convidar as pessoas para sua organização.

Algumas coisas lembrar:

- Para cada paga licença do Azure AD que você pode atribuir a um usuário, os usuários podem convidar usuários de convidado até cinco sob a permissão de usuário externo.
- Convidados são usuários fora da sua organização. Seus funcionários, prestadores de serviços no local, os operadores no local e assim por diante, não podem ser adicionados como convidados. O mesmo se aplica às suas afiliadas.
- As licenças de convidado são contadas contra a organização convidando. Considere isso ao calcular o número de licenças que necessárias.
- As licenças são contadas contra a sua organização se os convidados vêm de outro locatário do Office 365 ou estiver usando seus endereços de email pessoais.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Etapa 1: definir as configurações no Azure AD business-to-business

1. Entrar nohttps://portal.azure.com
2. No painel esquerdo, clique em **do Azure Active directory** .
3. Em **Gerenciar**, clique em **configurações do usuário**.
4. Em **usuários externos**, clique em **configurações de gerenciar externo de colaboração**.
5. Na página **configurações de colaboração externa** , certifique-se de **que membros podem convidar** estiver definida como **Sim**.

      ![Captura de tela mostra um exemplo de uma alternância de configurações AAD. ](media/guest-access-checklist-AADSettings1.png)

    Para suportar os convidados, **os membros podem convidar** deve ser definida como **Sim**. 
   
> [!NOTE] 
> Se você define **membros podem convidar** como **não** e, em seguida, habilita o acesso de convidado no Office 365 grupos e Teams da Microsoft, os administradores podem controlar a convites de convidado para seu diretório. Depois que os convidados estão no diretório, podem ser adicionados às equipes pelos membros não seja o administrador que são proprietários de equipe.

Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).


## <a name="-step-2-configure-office-365-groups"></a>□ Etapa 2: configurar grupos do Office 365

1. No Centro de administração do Microsoft 365, vá para **configurações** > **Serviços & suplementos** > **Grupos do Office 365**.
2. Certifique-se de **Permitir que os membros do grupo fora o conteúdo de grupo de acesso de organização** está definida como **On**. Se essa configuração estiver desativada, os convidados não conseguirá acessar nenhum conteúdo de grupo.
3. Certifique-se de **Permitir que os proprietários de grupo adicionar pessoas fora da organização para grupos** está definida como **On**. Se essa configuração estiver desativada, os proprietários de equipe não conseguirá adicionar novos convidados. No mínimo, essa configuração deve ser no suporte ao acesso de convidado.

     ![Captura de tela mostra as grupos comuta o Office 365](media/guest-access-checklist-office365.png)

Para obter instruções detalhadas sobre como definir essas configurações, consulte a seção "Office 365 grupos" em [autorizar o acesso de convidado em equipes da Microsoft](Teams-dependencies.md)e [Gerenciar o acesso de convidado em grupos do Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) .
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Etapa 3: habilitar o acesso de convidado a nível de locatário

No mínimo, você deve ativar acesso como convidado for Microsoft Teams sob o **Centro de administração de equipes da Microsoft**. 

1. No Centro de administração de equipes, selecione **configurações de toda a organização** > **acesso de convidado**.
2. Defina a opção de **Permitir o acesso de convidado em equipes da Microsoft** para **ativado**.

    ![Captura de tela mostra um exemplo de uma alternância de configurações de equipes](media/guest-access-checklist-set-up-guests-image1.png)

3. Nesta página mesmo, configure qualquer outra configuração de convidado que você precisa.
4. Clique em **Salvar**.

Para obter instruções detalhadas, consulte [Ativar ou desativar o acesso de convidado para equipes da Microsoft](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Etapa 4: configurar o compartilhamento no Office 365 

Certifique-se de que os usuários podem adicionar convidados. Veja como:

1. No Centro de administração do Microsoft 365, vá para **configurações** > **segurança & privacidade**.

     ![Captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Em **compartilhamento**, selecione **Editar**.

     ![Captura de tela mostra um exemplo de uma alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Definir **permitem aos usuários adicionar novos convidados para esta organização** para **ativado**e clique em **Salvar**.

     ![Captura de tela mostra um exemplo de uma alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Essa configuração equivale à configuração de **membros podem convidar** em **configurações do usuário** > **usuários externos** no Azure AD.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Etapa 5: verificar a configuração de compartilhamento no SharePoint

1. Entrar no Centro de administração do Microsoft 365.
2. Clique em **Administração Central**e selecione **SharePoint**.
3. No Centro de administração do SharePoint, selecione **compartilhamento**.
4. Verifique se a opção para **não permitir o compartilhamento fora da sua organização** *não* está selecionado.
 
     ![Captura de tela mostra um exemplo de uma alternância de configurações SparePoint Online.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Etapa 6: Habilitar configurações específicas para canais 

No aplicativo de equipes, no nível equipe individuais, configure permissões de convidado para que os convidados podem criar, atualizar e excluir canais. Além dos administradores, os proprietários de equipe podem configurar essa definição.

![Captura de tela mostra um exemplo de uma alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Para obter mais informações, incluindo vídeos de instruções, consulte [acesso de convidado em equipes da Microsoft](guest-access.md).


## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas com a adição de convidados no Teams da Microsoft, consulte o [Guia de solução de problemas de acesso de convidado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


