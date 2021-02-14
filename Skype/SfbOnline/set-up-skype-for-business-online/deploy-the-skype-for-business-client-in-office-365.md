---
title: Implantar o cliente Skype for Business no Microsoft 365 ou office 365
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
description: 'Saiba como planejar e implantar o Skype for Business em organizações de pequeno, médio e grande porte e disponibilizando-o para seus usuários. '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777236"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implantar o cliente Skype for Business no Microsoft 365 ou no Office 365

Este artigo explica as opções de como você, o **[administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** pode implantar o aplicativo Skype for Business para as pessoas em sua organização.
  
Antes de implantar o Skype for Business para seus usuários, certifique-se de ter realizado as etapas de 1 a 3 no artigo [Configurar o Skype for Business Online.](set-up-skype-for-business-online.md) Dessa forma, o Skype for Business será configurado com seu domínio, todos terão suas licenças, e você terá configurado as mensagens de iM e configurar a presença no [Skype for Business Online](configure-presence-in-skype-for-business-online.md) para sua organização.
  
> [!NOTE]
> Para que os usuários instalem o aplicativo Skype for Business, eles precisam ser administradores locais em seus computadores ou dispositivos. Ou eles precisarão fazer parte de um grupo local que possa instalar aplicativos em seus computadores ou dispositivos. Se os usuários não têm permissão para instalar o software em seus dispositivos, você precisará instalar o aplicativo Skype for Business para eles. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para a maioria das pequenas e médias empresas

 **Instruções de instalação passo a passo:** Se você tem uma empresa de pequeno ou médio porte, recomendamos que você simplesmente peça aos usuários para instalarem o aplicativo Skype for Business em seus computadores. Aponte-os para estas instruções: [Instalar o Skype for Business.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Se eles estão usando Macs, aponte-os para Configurar o [Lync para Mac 2011 para Office 365.](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) O aplicativo Skype for Business é instalado separadamente do restante dos aplicativos do Office.
  
 **Aplicativos do Microsoft 365 para clientes corporativos:** Se a sua empresa estiver usando um plano do Office 365 que inclua aplicativos do Microsoft 365 para empresas, como o plano E3, o aplicativo Skype for Business será instalado ao mesmo tempo em que os usuários baixam e instalam o Word, o Excel, o PowerPoint etc. Isso também significa que eles não podem desinstalar o Skype for Business, a menos que desinstale todo o Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Escolha se você quer disponibilizar o Skype for Business para seus usuários

Como [administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) você pode optar por disponibilizar o aplicativo Skype for Business para seus usuários.
  
- Para controlar se todos em sua empresa têm o **software:** entre no Centro de administração do Microsoft 365, vá para Instalar meu software e selecione o **software** que você deseja que fique disponível para os usuários.
    
    ![Escolha o software que você deseja disponibilizar para as pessoas em sua empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Para controlar se pessoas específicas em sua empresa receberão o **software:** entre no Centro de administração do Microsoft 365, vá para Usuários Ativos, selecione a pessoa que você deseja dar acesso ao software e clique em Editar ao lado das  >   **licenças** de Produto e a ligue ou desabilite. 
    
    ![Escolha qual software você deseja que o usuário acesse.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se você precisar ver quais planos estão atribuídos às pessoas em sua organização, entre no Centro de administração do Microsoft 365 > **Usuários**  >  **Ativos.** Selecione a pessoa na lista e procure em **Licenças de produto.** Se você estiver usando o centro de administração clássico, procure em **Licença atribuída.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implantando manualmente o Skype for Business para seus usuários
<a name="bkmk_manual_1"> </a>

Se quiser que os usuários instalem o aplicativo Skype for Business de um local na sua rede em vez da Internet, você pode baixar os arquivos de configuração. Para fazer isso, vá para a **seção de software de implantação manual** do usuário do Centro de administração do Microsoft 365. Em seguida, você pode **selecionar Instalar** e salvar o arquivo .exe de configuração em um local de rede.
  
Outra opção é baixar o aplicativo Skype for Business Basic para seus usuários. Você pode baixar [o Microsoft Skype for Business Basic (32 ou 64 bits).](https://www.microsoft.com/download/details.aspx?id=49440)
  
Para os aplicativos completos e básicos do Skype for Business, depois de baixar os arquivos de configuração, você precisará enviar manualmente (por exemplo, por email) o caminho de rede para os usuários para que eles possam executar o programa de configuração para instalar o aplicativo em seus computadores.
  
Você também pode usar esses downloads para implantar o aplicativo Skype for Business para seus usuários usando suas ferramentas e processos de implantação de software existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizações maiores e corporativas

> [!NOTE]
> Esta seção se aplica apenas ao aplicativo Skype for Business disponível por meio de planos do Office 365. Se sua organização estiver usando uma versão licenciada por volume do aplicativo Skype for Business, que é baseado no Windows Installer (MSI), confira Personalizar a instalação do cliente [windows no Skype for Business Server.](https://technet.microsoft.com/library/jj204934.aspx)
  
Em muitas empresas ou organizações de grande porte, os usuários não têm permissão para instalar o software em seus computadores. Em vez disso, os departamentos de IT implantam o software necessário nos computadores dos usuários. Os departamentos de IT também podem querer controlar a quantidade de largura de banda de Internet ou de rede usada em sua organização, para que eles possam instalar o software de um local próximo em sua rede, em vez de na Internet ou na rede corporativa.
  
Com o Office 365, você tem várias opções para implantar o aplicativo Skype for Business se quiser controlar de onde ele está instalado. Algumas dessas opções incluem o seguinte:
  
- Baixe o aplicativo Skype for Business para sua rede local no Centro de administração do Microsoft 365, conforme descrito em Implantação manual do [Skype for Business para seus usuários.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Use a **[Ferramenta de Implantação](https://go.microsoft.com/fwlink/p/?LinkID=626065)** do Office para baixar aplicativos do Microsoft 365 para empresas ou o aplicativo Skype for Business para sua rede local. Em seguida, use a Ferramenta de Implantação do Office para implantar o aplicativo para seus usuários. A Ferramenta de Implantação do Office oferece a capacidade de controlar determinados aspectos da implantação, como idiomas e versão (32 bits ou 64 bits).
    
- Use suas ferramentas e processos de implantação de software existentes, como o Microsoft Endpoint Configuration Manager, para implantar o Microsoft 365 Apps para empresas ou o aplicativo Skype for Business para seus usuários. Você pode usar suas ferramentas e processos existentes com a Ferramenta de Implantação do [Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou com o software que baixou do Centro de administração do Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Mais informações sobre como usar a Ferramenta de Implantação do Office

Para obter detalhes sobre como baixar a Ferramenta de Implantação do Office e mais informações sobre como instalar o aplicativo Skype for Business e outros aplicativos cliente do Office 365, consulte Gerenciar configurações de download de software no [Office 365.](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)
  
Aqui está uma visão geral das etapas envolvidas no uso da Ferramenta de Implantação do Office para implantar um aplicativo:
  
1. **[Baixe a Ferramenta de Implantação do Office mais](https://www.microsoft.com/download/details.aspx?id=49117)** recente do Centro de Download da Microsoft.
    
2. Crie o arquivo configuration.xml a ser usado com a Ferramenta de Implantação do Office que tem as configurações do aplicativo cliente que você deseja, como definir a versão (32 bits ou 64 bits), o idioma de instalação etc.
    
3. Use a Ferramenta de Implantação do Office e o arquivo configuration.xml para baixar os arquivos de configuração para sua rede local ou interna da Rede de Distribuição de Conteúdo (CDN) do Office.
    
4. Use a Ferramenta de Implantação do Office e a configuration.xml para instalar os aplicativos cliente do Office, incluindo o aplicativo Skype for Business.
    
Para obter detalhes sobre como usar a Ferramenta de Implantação do Office configuration.xml arquivo, consulte os seguintes artigos:
  
- [Visão geral da Ferramenta de Implantação do Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml configurações](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Mais informações sobre como usar o Microsoft Endpoint Configuration Manager

Você pode usar suas ferramentas e processos de implantação de software existentes, como o Microsoft Endpoint Configuration Manager, para implantar o aplicativo Skype for Business. Você pode usar essas ferramentas e processos com o software baixado do Centro de administração do Microsoft 365 ou com a Ferramenta de Implantação do Office.
  
Para obter mais informações sobre como usar o Configuration Manager para implantar o software, consulte os seguintes artigos:
  
- [Criar aplicativos no Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Implantar aplicativos com o Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Se você estiver implantando o aplicativo Skype for Business como parte da implantação de aplicativos do Microsoft 365 para empresas, consulte Gerenciar aplicativos do [Microsoft 365](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)para empresas com o Configuration Manager.
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planejamento de atualizações para o aplicativo Skype for Business

Como parte da implantação do aplicativo Skype for Business, você precisa considerar como deseja obter atualizações após a instalação do Skype for Business. Essas atualizações podem incluir novos recursos, atualizações de segurança ou atualizações que não são de segurança, como atualizações que fornecem melhorias de estabilidade ou desempenho. As duas principais coisas que você precisa considerar são:
  
- De onde você deseja obter atualizações
    
- Com que frequência você deseja obter atualizações de recursos
    
Embora você possa controlar de onde você recebe atualizações e com que frequência recebe atualizações de recursos, não é possível escolher quais atualizações de segurança específicas ou não de segurança você recebe.
  
 **De onde obter atualizações**
  
Por padrão, após a instalação do aplicativo Skype for Business, as atualizações serão baixadas automaticamente da Internet quando elas estão disponíveis na Microsoft. Se quiser ter mais controle sobre quando as atualizações ocorrem ou de onde as atualizações são instaladas, você pode usar a Ferramenta de Implantação do Office ou a Política de Grupo para configurá-la.
  
Por exemplo, muitas organizações querem testar atualizações com um grupo de usuários antes de implantá-las em toda a organização. Você pode fazer isso usando a Ferramenta de Implantação do Office ou a Política de Grupo para configurar o aplicativo Skype for Business para obter atualizações de um local específico em sua rede, em vez de automaticamente da Internet. Em seguida, você pode usar a Ferramenta de Implantação do Office para baixar as atualizações todos os meses em sua rede local.
  
Para saber mais sobre como funcionam as atualizações para o software do Office 365, consulte estes artigos:
  
- [Visão geral do processo de atualização para aplicativos do Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Escolha como gerenciar atualizações para aplicativos do Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Definir configurações de atualização para aplicativos do Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761708.aspx)
    
  **Com que frequência obter atualizações de recursos**
  
Além de onde você recebe atualizações, você também pode controlar a frequência com que recebe novos recursos para o cliente Skype for Business. As duas opções são as seguintes:
  
- Obter atualizações de recursos todos os meses, se houver novos recursos
    
- Obter atualizações de recursos a cada seis meses
    
Para algumas organizações, elas querem tempo para testar novos recursos, portanto, querem receber atualizações de recursos apenas duas vezes por ano em vez de todos os meses.
  
Você pode controlar a frequência com que recebe atualizações de recursos usando a Ferramenta de Implantação do Office ou a Política de Grupo para configurar o canal de atualização. O Canal Mensal fornece atualizações de recursos mensais (aproximadamente), enquanto o Canal Semi-Annual oferece atualizações de recursos a cada seis meses. Para obter mais informações sobre canais, consulte Visão geral dos canais de atualização [para aplicativos do Microsoft 365 para empresas.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>Tópicos relacionados

[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
