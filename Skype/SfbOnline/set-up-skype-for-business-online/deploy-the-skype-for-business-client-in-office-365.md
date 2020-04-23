---
title: Implantar o cliente Skype for Business no Microsoft 365 AOR o Office 365
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
description: 'Saiba como planejar e implantar o Skype for Business em organizações pequenas, médias e grandes e disponibilizá-lo para seus usuários. '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777236"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implantar o cliente Skype for Business no Microsoft 365 ou no Office 365

Este artigo explica as opções sobre como você, o **[administrador](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** pode implantar o aplicativo Skype for Business para as pessoas em sua organização.
  
Antes de implantar o Skype for Business para seus usuários, verifique se você concluiu as etapas 1-3 no artigo [Configurar o Skype for Business online](set-up-skype-for-business-online.md). Dessa forma, o Skype for Business será configurado com o seu domínio, todos terão suas licenças e você terá configurado mensagens instantâneas e [configuração de presença no Skype for Business online](configure-presence-in-skype-for-business-online.md) para sua organização.
  
> [!NOTE]
> Para que os usuários instalem o aplicativo Skype for Business, eles precisam ser administradores locais no PC ou dispositivo. Ou eles precisarão fazer parte de um grupo local que pode instalar aplicativos em seu PC ou dispositivos. Se os usuários não tiverem permissão para instalar o software em seus dispositivos, você precisará instalar o aplicativo Skype for Business para eles. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para a maioria das empresas de pequeno e médio porte

 **Instruções de instalação passo a passo:** Se você tiver uma pequena ou média empresa, recomendamos que você simplesmente solicite que os usuários instalem o aplicativo Skype for Business em seu computador. Aponte para estas instruções: [instalar o Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Se ele estiver usando Macs, aponte para [Configurar o Lync for Mac 2011 para o Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). O aplicativo Skype for Business é instalado separadamente do restante dos aplicativos do Office.
  
 **Aplicativos do Microsoft 365 para clientes empresariais:** Se a sua empresa estiver usando um plano do Office 365 que inclua aplicativos Microsoft 365 para empresas, como o plano E3, o aplicativo Skype for Business é instalado ao mesmo tempo em que os usuários baixam e instalam o Word, o Excel, o PowerPoint, etc. Isso também significa que não é possível desinstalar o Skype for Business, a menos que desinstalem todo o Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Escolha se deseja disponibilizar o Skype for Business para seus usuários

Como [administrador](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) , você pode escolher se deseja disponibilizar o aplicativo Skype for Business para seus usuários.
  
- **Para controlar se todas as pessoas da sua empresa recebem o software**: entre no centro de administração do Microsoft 365, vá para **instalar meu software**e, em seguida, selecione o software que você deseja disponibilizar para os usuários.
    
    ![Escolha o software que você deseja disponibilizar para as pessoas em sua empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Para controlar se as pessoas específicas da sua empresa obtêm o software**: entre no centro de administração do Microsoft 365, **vá para** > **usuários ativos**do Microsoft, selecione a pessoa para quem você deseja conceder acesso ao software e clique em **Editar** ao lado de **licenças de produto** e ative ou desative a licença.
    
    ![Escolha o software que você deseja que o usuário acesse.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se você precisar ver quais planos são atribuídos às pessoas em sua organização, entre no centro de administração do Microsoft **365 >** > usuários**ativos**do Microsoft. Selecione a pessoa na lista e, em seguida, procure **licenças de produto**. Se você estiver usando o centro de administração clássico, procure em **licença atribuída**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implantação manual do Skype for Business para seus usuários
<a name="bkmk_manual_1"> </a>

Se quiser que os usuários instalem o aplicativo Skype for Business a partir de um local na sua rede, em vez da Internet, você pode baixar os arquivos de instalação. Para fazer isso, vá para a seção **implantar o software do usuário manualmente** do centro de administração do Microsoft 365. Em seguida, você pode selecionar **instalar** e salvar o arquivo setup. exe em um local de rede.
  
Outra opção é baixar o aplicativo Skype for Business Basic para seus usuários. Você pode baixar [o Microsoft Skype for Business Basic (32 ou 64 bit)](https://www.microsoft.com/download/details.aspx?id=49440).
  
Para os aplicativos completos e básicos do Skype for Business, depois de baixar os arquivos de instalação, você precisará enviar manualmente (por exemplo, em email) o caminho de rede para os usuários para que eles possam executar o programa de instalação para instalar o aplicativo em seu computador.
  
Você também pode usar esses downloads para implantar o aplicativo Skype for Business para seus usuários usando suas ferramentas e processos de implantação de software existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizações maiores e empresariais

> [!NOTE]
> Esta seção aplica-se somente ao aplicativo Skype for Business disponível através dos planos do Office 365. Se a sua organização estiver usando uma versão licenciada de volume do aplicativo Skype for Business, que é baseada no Windows Installer (MSI), consulte [Personalizar a instalação do Windows Client no Skype for Business Server](https://technet.microsoft.com/library/jj204934.aspx).
  
Em muitas empresas ou organizações grandes, os usuários não têm permissão para instalar o software em seus computadores. Em vez disso, os departamentos de ti implantam o software necessário nos computadores dos usuários. Os departamentos de ti também podem querer controlar a quantidade de largura de banda da Internet ou da rede usada em sua organização, portanto, eles querem instalar o software a partir de um local próximo em sua rede, e não pela Internet ou pela rede da empresa.
  
Com o Office 365, você tem várias opções para implantar o aplicativo Skype for Business, se quiser controlar a localização. Algumas dessas opções incluem o seguinte:
  
- Baixe o aplicativo Skype for Business para a sua rede local no centro de administração do Microsoft 365, conforme descrito em [implantação manual do Skype for Business para seus usuários](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Use a **[ferramenta de implantação do Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para baixar os aplicativos da Microsoft 365 para empresas ou o aplicativo Skype for Business para a sua rede local. Em seguida, use a ferramenta de implantação do Office para implantar o aplicativo para seus usuários. A ferramenta de implantação do Office oferece a capacidade de controlar determinados aspectos da implantação, como idiomas e versão (32 bits ou 64 bits).
    
- Use suas ferramentas e processos de implantação de software existentes, como o Microsoft Endpoint Configuration Manager, para implantar os aplicativos do Microsoft 365 para empresas ou o aplicativo Skype for Business para seus usuários. Você pode usar as ferramentas e processos existentes com a [ferramenta de implantação do Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou com o software que você baixou do centro de administração do Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Mais informações sobre como usar a ferramenta de implantação do Office

Para obter detalhes sobre o download da ferramenta de implantação do Office e mais informações sobre como instalar o aplicativo Skype for Business e outros aplicativos cliente do Office 365, consulte [gerenciar configurações de download de software no Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Aqui está uma visão geral das etapas envolvidas no uso da ferramenta de implantação do Office para implantar um aplicativo:
  
1. **[Baixe a ferramenta de implantação do Office mais recente](https://www.microsoft.com/download/details.aspx?id=49117)** no centro de download da Microsoft.
    
2. Crie o arquivo Configuration. XML a ser usado com a ferramenta de implantação do Office que tem as configurações de aplicativo cliente desejadas, como a configuração da versão (32 bits ou 64 bits), o idioma de instalação, etc.
    
3. Use a ferramenta de implantação do Office e o arquivo Configuration. xml para baixar os arquivos de instalação para sua rede local ou interna da CDN (rede de distribuição de conteúdo) do Office.
    
4. Use a ferramenta de implantação do Office e o Configuration. xml para instalar os aplicativos cliente do Office, incluindo o aplicativo Skype for Business.
    
Para obter detalhes sobre como usar a ferramenta de implantação do Office e o arquivo Configuration. xml, consulte os seguintes artigos:
  
- [Visão geral da ferramenta de implantação do Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configurações do Configuration. xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Mais informações sobre como usar o Gerenciador de configuração do Microsoft Endpoint

Você pode usar suas ferramentas e processos de implantação de software existentes, como o Microsoft Endpoint Configuration Manager, para implantar o aplicativo Skype for Business. Você pode usar essas ferramentas e processos com o software que você baixa no centro de administração do Microsoft 365 ou com a ferramenta de implantação do Office.
  
Para obter mais informações sobre como usar o Configuration Manager para implantar o software, consulte os seguintes artigos:
  
- [Criar aplicativos no Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Implantar aplicativos com o Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Se você estiver implantando o aplicativo Skype for Business como parte da implantação de aplicativos do Microsoft 365 para empresas, consulte [gerenciar aplicativos da microsoft 365 para empresas com o Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planejando atualizações para o aplicativo Skype for Business

Como parte da implantação do aplicativo Skype for Business, você precisa considerar como deseja obter atualizações após a instalação do Skype for Business. Essas atualizações podem incluir novos recursos, atualizações de segurança ou atualizações não relacionadas à segurança, como atualizações que fornecem melhorias de estabilidade e desempenho. As duas principais coisas que você precisa considerar são:
  
- De onde você deseja obter atualizações
    
- Com que frequência você deseja obter atualizações de recursos
    
Embora você possa controlar de onde você obtém atualizações e com que frequência Obtém atualizações de recursos, não é possível escolher quais atualizações de segurança específicas ou atualizações não relacionadas à segurança você obtém.
  
 **Para onde obter atualizações**
  
Por padrão, após a instalação do aplicativo Skype for Business, as atualizações serão baixadas automaticamente da Internet quando estiverem disponíveis para a Microsoft. Se quiser ter mais controle sobre quando ocorrem atualizações ou onde as atualizações são instaladas, você pode usar a ferramenta de implantação do Office ou a política de grupo para configurar isso.
  
Por exemplo, muitas organizações querem testar atualizações com um grupo de usuários antes de implantá-las em toda a organização. Você pode fazer isso usando a ferramenta de implantação do Office ou a política de grupo para configurar o aplicativo Skype for Business para obter atualizações de um local específico na sua rede, em vez de automaticamente da Internet. Em seguida, você pode usar a ferramenta de implantação do Office para baixar as atualizações mensalmente para a sua rede local.
  
Para obter mais informações sobre como as atualizações funcionam para o software do Office 365, consulte estes artigos:
  
- [Visão geral do processo de atualização para aplicativos do Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Escolher como gerenciar as atualizações para o Microsoft 365 aplicativos para empresas](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Definir configurações de atualização para aplicativos do Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761708.aspx)
    
  **Com que frequência obter atualizações de recursos**
  
Além de onde você obtém atualizações, você também pode controlar com que frequência Obtém novos recursos para o cliente Skype for Business. As duas opções são as seguintes:
  
- Obter atualizações de recursos todos os meses, se houver novos recursos
    
- Obter atualizações de recursos a cada seis meses
    
Para algumas organizações, eles querem tempo para testar novos recursos, para que eles queiram obter atualizações de recursos apenas duas vezes por ano, em vez de cada mês.
  
Você pode controlar com que frequência Obtém atualizações de recursos usando a ferramenta de implantação do Office ou a política de grupo para configurar o canal de atualização. O canal mensal oferece atualizações de recursos mensalmente (aproximadamente), enquanto o canal semestral oferece atualizações de recursos a cada seis meses. Para obter mais informações sobre canais, consulte [visão geral de canais de atualização para aplicativos do Microsoft 365 para empresas](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Tópicos relacionados

[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
