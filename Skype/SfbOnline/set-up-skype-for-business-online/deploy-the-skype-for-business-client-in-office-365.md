---
title: Implantar o cliente skype for Business no Microsoft 365 aor Office 365
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Saiba como planejar e implantar o Skype for Business em organizações pequenas, médias e grandes e disponibilizar para seus usuários. '
ms.openlocfilehash: 7a2ba51a315b77c501735be863f342c1bdb1548f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097287"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implantar o cliente Skype for Business no Microsoft 365 ou Office 365

Este artigo explica as opções de como você, o **[administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** pode implantar o aplicativo Skype for Business para as pessoas em sua organização.
  
Antes de implantar o Skype for Business para seus usuários, certifique-se de ter feito as etapas 1-3 no artigo [Configurar o Skype for Business Online](set-up-skype-for-business-online.md). Dessa forma, o Skype for Business será configurado com seu domínio, todos terão suas licenças e você terá configurado o IM e Configurará a presença no [Skype for Business Online](configure-presence-in-skype-for-business-online.md) para sua organização.
  
> [!NOTE]
> Para que os usuários instalem o aplicativo Skype for Business, eles precisam ser administradores locais em seu computador ou dispositivo. Ou eles precisarão fazer parte de um grupo local que pode instalar aplicativos em seus computadores ou dispositivos. Se os usuários não têm permissão para instalar software em seus dispositivos, você precisará instalar o aplicativo Skype for Business para eles. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para a maioria das pequenas e médias empresas

 **Instruções de instalação passo a passo:** Se você tiver uma pequena ou média empresa, recomendamos que você simplesmente peça aos usuários para instalar o aplicativo skype for Business em seu computador. Aponte-os para estas instruções: [Instalar o Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Se eles estão usando Macs, aponte-os para [Configurar o Lync para Mac 2011 para Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). O aplicativo skype for Business é instalado separadamente do restante dos aplicativos do Office.
  
 **Aplicativos do Microsoft 365 para clientes corporativos:** Se sua empresa estiver usando um plano do Office 365 que inclua o Microsoft 365 Apps para empresas, como o plano E3, o aplicativo skype for Business será instalado ao mesmo tempo em que os usuários baixam e instalam o Word, Excel, PowerPoint etc. Isso também significa que eles não podem desinstalar o Skype for Business, a menos que desinstale todo o Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Escolha se disponibiliza o Skype for Business para seus usuários

Como [administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) você pode optar por disponibilizar o aplicativo Skype for Business para seus usuários.
  
- **Para controlar** se todos em sua empresa obtém o software : entre no Centro de administração do Microsoft 365, vá para Instalar meu software e selecione o **software** que você deseja estar disponível para os usuários.
    
    ![Escolha o software que você deseja disponibilizar para as pessoas em sua empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Para controlar se pessoas específicas em sua empresa obterão o **software**: entre no Centro de administração do Microsoft 365, vá para Usuários ativos, selecione a pessoa que você deseja dar acesso ao software e clique em Editar ao lado de Licenças de produto e acione  >  ou desabilite a licença.  
    
    ![Escolha qual software você deseja que o usuário acesse.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se você precisar ver quais planos são atribuídos às pessoas em sua organização, entre no Centro de administração do Microsoft 365 > **Usuários**  >  **ativos**. Selecione a pessoa na lista e, em seguida, procure em **Licenças de produto**. Se você estiver usando o centro de administração clássico, procure em **Licença atribuída**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implantação manual do Skype for Business para seus usuários
<a name="bkmk_manual_1"> </a>

Se você quiser que seus usuários instalem o aplicativo Skype for Business de um local em sua rede, em vez da Internet, você pode baixar os arquivos de instalação. Para fazer isso, vá para a **seção Implantar manualmente o software do usuário** do Centro de administração do Microsoft 365. Em seguida, você pode **selecionar Instalar** e salvar o arquivo .exe de instalação em um local de rede.
  
Outra opção é baixar o aplicativo Skype for Business Basic para seus usuários. Você pode baixar [o Microsoft Skype for Business Basic (32 ou 64 bits)](https://www.microsoft.com/download/details.aspx?id=49440).
  
Para os aplicativos completos e básicos do Skype for Business, depois de baixar os arquivos de instalação, você precisará enviar manualmente (por exemplo, por email) o caminho de rede para os usuários para que eles possam executar o programa de instalação para instalar o aplicativo em seu computador.
  
Você também pode usar esses downloads para implantar o aplicativo Skype for Business para seus usuários usando suas ferramentas e processos de implantação de software existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizações maiores e corporativas

> [!NOTE]
> Esta seção só se aplica ao aplicativo Skype for Business disponível por meio de planos do Office 365. Se sua organização estiver usando uma versão licenciada por volume do aplicativo Skype for Business, que é baseada no Windows Installer (MSI), consulte Personalizar a instalação do cliente do Windows no [Skype for Business Server](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md).
  
Em muitas empresas ou grandes organizações, os usuários não têm permissão para instalar software em seus computadores. Em vez disso, os departamentos de IT implantam o software necessário para os computadores dos usuários. Os departamentos de IT também podem querer controlar a quantidade de internet ou largura de banda de rede usada em sua organização, portanto, eles querem instalar software de um local próximo em sua rede, em vez de na Internet ou na rede corporativa.
  
Com o Office 365, você tem várias opções para implantar o aplicativo Skype for Business se quiser controlar de onde ele está instalado. Algumas dessas opções incluem:
  
- Baixe o aplicativo Skype for Business para sua rede local do Centro de administração do Microsoft 365, conforme descrito em Implantação manual do [Skype for Business para seus usuários.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Use a **[Ferramenta de Implantação](https://go.microsoft.com/fwlink/p/?LinkID=626065)** do Office para baixar o Microsoft 365 Apps para empresas ou o aplicativo Skype for Business para sua rede local. Em seguida, use a Ferramenta de Implantação do Office para implantar o aplicativo para seus usuários. A Ferramenta de Implantação do Office oferece a capacidade de controlar determinados aspectos da implantação, como idiomas e versão (32 bits ou 64 bits).
    
- Use suas ferramentas e processos de implantação de software existentes, como o Microsoft Endpoint Configuration Manager, para implantar o Microsoft 365 Apps para empresas ou o aplicativo Skype for Business para seus usuários. Você pode usar suas ferramentas e processos existentes com a Ferramenta de Implantação do [Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou com o software que você baixou do centro de administração do Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Mais informações sobre como usar a Ferramenta de Implantação do Office

Para obter detalhes sobre como baixar a Ferramenta de Implantação do Office e mais informações sobre como instalar o aplicativo Skype for Business e outros aplicativos cliente do Office 365, consulte Gerenciar configurações de download de software no [Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Aqui está uma visão geral das etapas envolvidas no uso da Ferramenta de Implantação do Office para implantar um aplicativo:
  
1. **[Baixe a mais recente Ferramenta de Implantação do Office](https://www.microsoft.com/download/details.aspx?id=49117)** no Centro de Download da Microsoft.
    
2. Crie o arquivo configuration.xml a ser usado com a Ferramenta de Implantação do Office que tenha as configurações do aplicativo cliente que você deseja, como definir a versão (32 bits ou 64 bits), o idioma de instalação, etc.
    
3. Use a Ferramenta de Implantação do Office e o arquivo configuration.xml para baixar os arquivos de instalação para sua rede local ou interna da CdN (Rede de Distribuição de Conteúdo do Office).
    
4. Use a Ferramenta de Implantação do Office e a configuration.xml para instalar os aplicativos cliente do Office, incluindo o aplicativo Skype for Business.
    
Para obter detalhes sobre como usar a Ferramenta de Implantação do Office e o arquivo configuration.xml, consulte os seguintes artigos:
  
- [Visão geral da Ferramenta de Implantação do Office](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml configurações](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Mais informações sobre como usar o Microsoft Endpoint Configuration Manager

Você pode usar suas ferramentas e processos de implantação de software existentes, como o Microsoft Endpoint Configuration Manager, para implantar o aplicativo Skype for Business. Você pode usar essas ferramentas e processos com o software que você baixa do centro de administração do Microsoft 365 ou com a Ferramenta de Implantação do Office.
  
Para obter mais informações sobre como usar o Configuration Manager para implantar software, consulte os seguintes artigos:
  
- [Criar aplicativos no Configuration Manager](/configmgr/apps/deploy-use/create-applications)
    
- [Implantar aplicativos com o Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
    
Se você estiver implantando o aplicativo Skype for Business como parte da implantação do Microsoft 365 Apps para empresas, consulte [Manage Microsoft 365 Apps for enterprise with Configuration Manager](/configmgr/sum/deploy-use/manage-office-365-proplus-updates).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planejando atualizações para o aplicativo Skype for Business

Como parte da implantação do aplicativo Skype for Business, você precisa considerar como deseja obter atualizações após a instalação do Skype for Business. Essas atualizações podem incluir novos recursos, atualizações de segurança ou atualizações que não são de segurança, como atualizações que fornecem melhorias de estabilidade ou desempenho. As duas principais coisas que você precisa considerar são:
  
- De onde você deseja obter atualizações
    
- Com que frequência você deseja obter atualizações de recursos
    
Embora você possa controlar de onde você recebe atualizações e com que frequência recebe atualizações de recursos, não é possível escolher quais atualizações de segurança específicas ou atualizações que não são de segurança você recebe.
  
 **Onde obter atualizações**
  
Por padrão, após a instalação do aplicativo Skype for Business, as atualizações serão baixadas automaticamente da Internet quando elas estão disponíveis da Microsoft. Se você quiser mais controle sobre quando as atualizações ocorrerem ou de onde as atualizações são instaladas, você pode usar a Ferramenta de Implantação do Office ou a Política de Grupo para configurá-la.
  
Por exemplo, muitas organizações querem testar atualizações com um grupo de usuários antes de implantá-las em toda a organização. Você pode fazer isso usando a Ferramenta de Implantação do Office ou a Política de Grupo para configurar o aplicativo skype for Business para obter atualizações de um local específico em sua rede, em vez de automaticamente da Internet. Em seguida, você pode usar a Ferramenta de Implantação do Office para baixar as atualizações todos os meses para sua rede local.
  
Para obter mais informações sobre como as atualizações funcionam para o software do Office 365, consulte estes artigos:
  
- [Visão geral do processo de atualização para Aplicativos do Microsoft 365 para empresas](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [Escolha como gerenciar atualizações do Microsoft 365 Apps para empresas](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [Configurar configurações de atualização para Aplicativos do Microsoft 365 para empresas](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **Com que frequência obter atualizações de recursos**
  
Além de onde você recebe atualizações, você também pode controlar a frequência com que você recebe novos recursos para o cliente skype for Business. As duas opções são as seguintes:
  
- Obter atualizações de recursos todos os meses, se houver novos recursos
    
- Obter atualizações de recursos a cada seis meses
    
Para algumas organizações, elas querem tempo para testar novos recursos, portanto, elas querem receber atualizações de recursos apenas duas vezes por ano, em vez de todos os meses.
  
Você pode controlar a frequência com que recebe atualizações de recursos usando a Ferramenta de Implantação do Office ou a Política de Grupo para configurar o canal de atualização. O Canal Mensal fornece atualizações de recursos mensalmente (aproximadamente), enquanto o canal Semi-Annual fornece atualizações de recursos a cada seis meses. Para obter mais informações sobre canais, consulte [Overview of update channels for Microsoft 365 Apps for enterprise](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Tópicos relacionados

[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
