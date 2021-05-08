---
title: Implantar o Skype for Business cliente em Microsoft 365 ou Office 365
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
description: 'Saiba como planejar e implantar Skype for Business pequenas, médias e grandes organizações e disponibilizar para seus usuários. '
ms.openlocfilehash: e23d4310d47bfae68a12c2b928741a2994588a57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239894"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implantar o Skype for Business cliente no Microsoft 365 ou Office 365

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo explica as opções de como você, o **[administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** pode implantar o aplicativo Skype for Business para as pessoas em sua organização.
  
Antes de implantar Skype for Business para seus usuários, certifique-se de ter feito as etapas 1-3 no artigo Configurar o Skype for Business [Online](set-up-skype-for-business-online.md). Dessa forma, Skype for Business será configurado com seu domínio, todos terão suas licenças e você terá configurado o IM e [Configurará a](configure-presence-in-skype-for-business-online.md) presença no Skype for Business Online para sua organização.
  
> [!NOTE]
> Para os usuários instalarem o aplicativo Skype for Business, eles precisam ser administradores locais em seu computador ou dispositivo. Ou eles precisarão fazer parte de um grupo local que pode instalar aplicativos em seus computadores ou dispositivos. Se os usuários não têm permissão para instalar software em seus dispositivos, você precisará instalar o aplicativo Skype for Business para eles. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para a maioria das pequenas e médias empresas

 **Instruções de instalação passo a passo:** Se você tiver uma pequena ou média empresa, recomendamos que você simplesmente peça aos usuários para instalar o aplicativo Skype for Business no computador. Aponte-os para estas instruções: [Instalar Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Se eles estão usando Macs, aponte-os para [Configurar o Lync para Mac 2011 para Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). O Skype for Business aplicativo é instalado separadamente do restante dos Office aplicativos.
  
 **Microsoft 365 Apps para Grandes Empresas clientes:** Se sua empresa estiver usando um plano de Office 365 que inclui o Microsoft 365 Apps para Grandes Empresas, como o plano E3, o aplicativo do Skype for Business é instalado ao mesmo tempo em que os usuários baixam e instalam o Word, Excel, PowerPoint etc. Isso também significa que eles não podem desinstalar Skype for Business a menos que desinstale todos os Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Escolha se o Skype for Business disponível para seus usuários

Como [administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) você pode optar por disponibilizar o aplicativo Skype for Business para os usuários.
  
- **Para controlar se** todos em sua empresa obtém o software : entre no centro de administração do Microsoft 365, vá para Instalar meu software e selecione o **software** que você deseja estar disponível para os usuários.
    
    ![Escolha o software que você deseja disponibilizar para as pessoas em sua empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Para controlar se pessoas específicas da sua empresa obterão o **software**: entre no centro de administração do Microsoft 365, vá para **Usuários** ativos, selecione a pessoa que você deseja dar acesso ao software e clique em Editar ao lado de Licenças de produto e acione  >  ou desabilite a licença.  
    
    ![Escolha qual software você deseja que o usuário acesse.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se você precisar ver quais planos são atribuídos às pessoas em sua organização, entre no centro de administração Microsoft 365 > **usuários**  >  **ativos**. Selecione a pessoa na lista e, em seguida, procure em **Licenças de produto**. Se você estiver usando o centro de administração clássico, procure em **Licença atribuída**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implantando manualmente Skype for Business para seus usuários
<a name="bkmk_manual_1"> </a>

Se você quiser que seus usuários instalem o aplicativo Skype for Business de um local em sua rede, em vez da Internet, você pode baixar os arquivos de instalação. Para fazer isso, vá para a **seção Implantar manualmente o software do usuário** do Microsoft 365 de administração. Em seguida, você pode **selecionar Instalar** e salvar o arquivo .exe de instalação em um local de rede.
  
Outra opção é baixar o aplicativo Skype for Business Basic para seus usuários. Você pode baixar [o Microsoft Skype for Business Basic (32 ou 64 bits)](https://www.microsoft.com/download/details.aspx?id=49440).
  
Para os aplicativos completos e básicos Skype for Business, depois de baixar os arquivos de instalação, você precisará enviar manualmente (por exemplo, por email) o caminho de rede para os usuários para que eles possam executar o programa de instalação para instalar o aplicativo em seu computador.
  
Você também pode usar esses downloads para implantar o aplicativo Skype for Business para seus usuários usando suas ferramentas e processos de implantação de software existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizações maiores e corporativas

> [!NOTE]
> Esta seção só se aplica ao aplicativo Skype for Business disponível por meio Office 365 planos. Se sua organização estiver usando uma versão licenciada por volume do aplicativo Skype for Business, que é baseada em Windows Installer (MSI), consulte [Customize Windows client installation in Skype for Business Server](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md).
  
Em muitas empresas ou grandes organizações, os usuários não têm permissão para instalar software em seus computadores. Em vez disso, os departamentos de IT implantam o software necessário para os computadores dos usuários. Os departamentos de IT também podem querer controlar a quantidade de internet ou largura de banda de rede usada em sua organização, portanto, eles querem instalar software de um local próximo em sua rede, em vez de na Internet ou na rede corporativa.
  
Com Office 365, você tem várias opções para implantar o aplicativo Skype for Business se quiser controlar de onde ele está instalado. Algumas dessas opções incluem:
  
- Baixe o Skype for Business para sua rede local no centro de administração Microsoft 365, conforme descrito em Implantação manual Skype for Business [para seus usuários.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Use a **[Office de](https://go.microsoft.com/fwlink/p/?LinkID=626065)** Implantação para baixar o Microsoft 365 Apps para Grandes Empresas ou o aplicativo Skype for Business para sua rede local. Em seguida, use a Office de Implantação para implantar o aplicativo para seus usuários. A Office de Implantação oferece a capacidade de controlar determinados aspectos da implantação, como idiomas e versão (32 bits ou 64 bits).
    
- Use suas ferramentas e processos de implantação de software existentes, como Microsoft Endpoint Configuration Manager, para implantar o Microsoft 365 Apps para Grandes Empresas ou o aplicativo Skype for Business para seus usuários. Você pode usar suas ferramentas e processos existentes com [a](https://go.microsoft.com/fwlink/p/?LinkID=626065) Ferramenta de Implantação Office ou com o software que você baixou do centro de administração Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Mais informações sobre como usar a ferramenta Office implantação

Para obter detalhes sobre como baixar Office Ferramenta de Implantação do Office e mais informações sobre como instalar o aplicativo Skype for Business e outros aplicativos cliente Office 365, consulte [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Aqui está uma visão geral das etapas envolvidas no uso da Ferramenta de Implantação Office para implantar um aplicativo:
  
1. **[Baixe a ferramenta de implantação Office mais recente](https://www.microsoft.com/download/details.aspx?id=49117)** do Centro de Download da Microsoft.
    
2. Crie o arquivo configuration.xml a ser usado com a Ferramenta de Implantação do Office que tem as configurações do aplicativo cliente que você deseja, como definir a versão (32 bits ou 64 bits), o idioma de instalação, etc.
    
3. Use a Office de Implantação e o arquivo configuration.xml para baixar os arquivos de instalação para sua rede local ou interna do Office Rede de Distribuição de Conteúdo (CDN).
    
4. Use Office Ferramenta de Implantação e o configuration.xml para instalar os aplicativos Office cliente, incluindo o aplicativo Skype for Business.
    
Para obter detalhes sobre como usar o Office de implantação e o arquivo configuration.xml de implantação, consulte os seguintes artigos:
  
- [Office Visão geral da Ferramenta de Implantação](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml configurações](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Mais informações sobre como usar Microsoft Endpoint Configuration Manager

Você pode usar suas ferramentas e processos de implantação de software existentes, como Microsoft Endpoint Configuration Manager, para implantar o Skype for Business aplicativo. Você pode usar essas ferramentas e processos com o software que você baixa do centro de administração Microsoft 365 ou com a Office de Implantação.
  
Para obter mais informações sobre como usar o Configuration Manager para implantar software, consulte os seguintes artigos:
  
- [Criar aplicativos no Configuration Manager](/configmgr/apps/deploy-use/create-applications)
    
- [Implantar aplicativos com o Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
    
Se você estiver implantando o aplicativo Skype for Business como parte da implantação Microsoft 365 Apps para Grandes Empresas, consulte [Manage Microsoft 365 Apps para Grandes Empresas with Configuration Manager](/configmgr/sum/deploy-use/manage-office-365-proplus-updates).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planejando atualizações para o Skype for Business app

Como parte da implantação do aplicativo Skype for Business, você precisa considerar como deseja obter atualizações depois que Skype for Business é instalado. Essas atualizações podem incluir novos recursos, atualizações de segurança ou atualizações que não são de segurança, como atualizações que fornecem melhorias de estabilidade ou desempenho. As duas principais coisas que você precisa considerar são:
  
- De onde você deseja obter atualizações
    
- Com que frequência você deseja obter atualizações de recursos
    
Embora você possa controlar de onde você recebe atualizações e com que frequência recebe atualizações de recursos, não é possível escolher quais atualizações de segurança específicas ou atualizações que não são de segurança você recebe.
  
 **Onde obter atualizações**
  
Por padrão, depois que o aplicativo Skype for Business for instalado, as atualizações serão baixadas automaticamente da Internet quando elas estão disponíveis da Microsoft. Se você quiser mais controle sobre quando as atualizações ocorrerem ou de onde as atualizações são instaladas, você pode usar a Ferramenta de Implantação Office ou a Política de Grupo para configurá-la.
  
Por exemplo, muitas organizações querem testar atualizações com um grupo de usuários antes de implantá-las em toda a organização. Você pode fazer isso usando a Ferramenta de Implantação Office ou a Política de Grupo para configurar o aplicativo Skype for Business para obter atualizações de um local específico em sua rede, em vez de automaticamente da Internet. Em seguida, você pode usar Office Ferramenta de Implantação para baixar as atualizações todos os meses para sua rede local.
  
Para obter mais informações sobre como as atualizações funcionam Office 365 software, consulte estes artigos:
  
- [Visão geral do processo de atualização para Microsoft 365 Apps para Grandes Empresas](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [Escolha como gerenciar atualizações para Microsoft 365 Apps para Grandes Empresas](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [Configurar configurações de atualização para Microsoft 365 Apps para Grandes Empresas](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **Com que frequência obter atualizações de recursos**
  
Além de onde você recebe atualizações, você também pode controlar a frequência com que você recebe novos recursos para o cliente Skype for Business cliente. As duas opções são as seguintes:
  
- Obter atualizações de recursos todos os meses, se houver novos recursos
    
- Obter atualizações de recursos a cada seis meses
    
Para algumas organizações, elas querem tempo para testar novos recursos, portanto, elas querem receber atualizações de recursos apenas duas vezes por ano, em vez de todos os meses.
  
Você pode controlar a frequência com que recebe atualizações de recursos usando a Ferramenta de Implantação Office ou a Política de Grupo para configurar o canal de atualização. O Canal Mensal fornece atualizações de recursos mensalmente (aproximadamente), enquanto o canal Semi-Annual fornece atualizações de recursos a cada seis meses. Para obter mais informações sobre canais, consulte [Overview of update channels for Microsoft 365 Apps para Grandes Empresas](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Tópicos relacionados

[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
