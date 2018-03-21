---
title: "Implantar o Skype para o cliente de negócios no Office 365"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Saiba como planejar e implantar Skype para negócios em organizações pequenas, médias e grandes e tornar disponível aos usuários. "
ms.openlocfilehash: 09600c29d2df0299f326e64f75c6b4b7e5ee5178
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2018
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Implantar o Skype para o cliente de negócios no Office 365

Este artigo explica as opções de como você, o **[administrador](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, pode implantar o Skype para o aplicativo de negócios para as pessoas na sua organização.
  
Antes de implantar o Skype para negócios para seus usuários, verifique se tiver concluído as etapas 1-3 no artigo [Configure Skype para negócios Online](set-up-skype-for-business-online.md). Dessa forma, Skype para negócios será configurado com seu domínio, todos terão suas licenças e você será configurou IM e [presença de Configure em Skype para Business Online](configure-presence-in-skype-for-business-online.md) para sua organização.
  
> [!NOTE]
> Para os usuários instalem o Skype para o aplicativo de negócios, eles precisam ser administradores locais em seu PC ou dispositivo. Ou, eles precisarão fazer parte de um grupo local que pode instalar aplicativos em seu PC ou dispositivos. Se os usuários não têm permissão para instalar software em seus dispositivos, você precisará instalar o Skype para o aplicativo de negócios para eles. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para a maioria das empresas de pequeno e médio porte

 **Instruções de instalação passo a passo:** Se você tiver um negócio pequeno ou médias, recomendamos que você simplesmente pedir que os usuários instalem o Skype para o aplicativo de negócios no PC. Apontá-los para estas instruções: [Instale o Skype para negócios](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). Se estiverem usando Macs, apontá-los para [Configurar o Lync para Mac 2011 para o Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). O Skype para negócios app é instalado separadamente do resto do Office apps.
  
 **Clientes do office 365 ProPlus:** Se sua empresa estiver usando um plano do Office 365 que inclui o Office 365 ProPlus, como o plano E3, o Skype para negócios app é instalado ao mesmo tempo seus usuários baixar e instalar o Word, Excel, PowerPoint, etc. Isso também significa que eles não é possível desinstalar o Skype para os negócios, a menos que eles desinstalar todo o Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Escolha se deseja disponibilizar Skype for Business para seus usuários

Como o [administrador](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) , você pode escolher se deseja disponibilizar o Skype para o aplicativo de negócios para seus usuários.
  
- **Para controlar se todas as pessoas da sua empresa obtém o software**: entrar com o Office 365 Centro de administração, vá para **instalar o software**e selecione o software que você deseja disponibilizar para usuários.
    
    ![Escolha o software que você deseja disponibilizar para as pessoas da sua empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Para controlar se as pessoas específicas da sua empresa obtém o software**: entrar com o Office 365 Centro de administração, vá para **usuários** > **usuários ativos**, selecione a pessoa que você deseja conceder acesso ao software e clique em **Editar** ao lado de **licenças do produto** e ativar ou desativar o a licença.
    
    ![Escolha o software que você deseja que o usuário acesse.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se você precisar ver quais planos estão atribuídos a pessoas da sua organização, entrar com o novo centro de administração do Office 365 > **usuários** > **usuários ativos**. Selecione a pessoa na lista e procure em **licenças do produto**. Se você estiver usando o Centro de administração do Office 365 clássico, procure em **licença atribuído**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implantando manualmente Skype for Business para seus usuários
<a name="bkmk_manual_1"> </a>

Se desejar que os usuários instalem o Skype para o aplicativo de negócios de um local na rede, em vez da Internet, você pode baixar os arquivos de instalação. Para fazer essa ir para a seção **implantar manualmente o software do usuário** do Centro de administração do Office 365. Você pode, em seguida, selecione **instalar** e salve o arquivo de instalação .exe em um local de rede.
  
Outra opção é baixar o Skype para app básica de negócios para seus usuários. Você pode baixar o [Microsoft Skype para negócios básico (32 ou 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Para ambas a completo e básica Skype para aplicativos de negócios, depois que você baixou os arquivos de instalação, você precisará manualmente enviar (por exemplo, em email) o caminho de rede para os usuários para o programa de instalação para instalar o aplicativo em seu próprio computador possa ser executada.
  
Você também pode usar esses downloads para implantar o Skype para o aplicativo de negócios para seus usuários usando suas ferramentas de implantação existente do software e processos.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para maior e organizações empresariais

> [!NOTE]
> Esta seção se aplica somente a Skype para aplicativo de negócios disponível nos planos do Office 365. Se sua organização estiver usando uma versão de licença de volume do Skype para aplicativo de negócios, que é baseado no Windows Installer (MSI), consulte [Personalizar a instalação de cliente no Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
Em muitas empresas ou grandes empresas, os usuários não têm permissão para instalar software em seus computadores. Em vez disso, os departamentos de TI a implantar o software necessário aos computadores dos usuários. Departamentos de TI também talvez queira controlar a largura de banda de rede ou Internet usada na sua organização, portanto, eles desejam instalar o software de um local por perto em sua rede, em vez pela Internet ou na rede corporativa.
  
Com o Office 365, você tem várias opções para implantar o Skype para o aplicativo de negócios se você deseja controlar onde ele é instalado. Alguns dessas opções incluem o seguinte:
  
- Baixe o Skype para o aplicativo de negócios em sua rede local do Centro de administração do Office 365, conforme descrito em [Implantando manualmente Skype for Business para seus usuários](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Use a **[Ferramenta de implantação do Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para baixar o Skype para o aplicativo de negócios ou Office 365 ProPlus em sua rede local. Em seguida, use a ferramenta de implantação do Office para implantar o aplicativo para seus usuários. A ferramenta de implantação do Office oferece a capacidade de controlar certos aspectos da implantação, linguagens e versão (32 bits ou 64 bits).
    
- Use suas ferramentas de implantação existente do software e processos, como o System Center Configuration Manager, para implantar o Office 365 ProPlus ou o Skype para o aplicativo de negócios para seus usuários. Você pode usar seus processos e ferramentas existentes com a [Ferramenta de implantação do Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou com o software que você tenha baixado do Centro de administração do Office 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Mais informações sobre como usar a ferramenta de implantação do Office

Para obter detalhes sobre como baixar a ferramenta de implantação do Office e para obter mais informações sobre como instalar o Skype para aplicativos de negócios e outros aplicativos de cliente do Office 365, consulte [Gerenciar o software do usuário no Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Aqui está uma visão geral das etapas envolvidas na usando a ferramenta de implantação do Office para implantar um aplicativo:
  
1. **[Baixe a ferramenta de implantação do Office mais recente](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** do Microsoft Download Center.
    
2. Crie o arquivo Configuration. XML para ser usado com a ferramenta de implantação do Office com as configurações do aplicativo cliente desejada, como a configuração da versão (32 bits ou 64 bits), o idioma de instalação, etc.
    
3. Use a ferramenta de implantação do Office e o arquivo Configuration para baixar os arquivos de instalação em sua rede local ou interno da rede de entrega conteúdo do Office (CDN).
    
4. Use a ferramenta de implantação do Office e o Configuration para instalar os aplicativos cliente do Office, incluindo o Skype para o aplicativo de negócios.
    
Para obter detalhes sobre como usar a ferramenta de implantação do Office e o arquivo Configuration XML, consulte os seguintes artigos:
  
- [Visão geral da ferramenta de implantação do Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configurações de Configuration. XML](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>Mais informações sobre como usar o System Center Configuration Manager

Você pode usar suas ferramentas de implantação existente do software e processos, como o System Center Configuration Manager, para implantar o Skype para o aplicativo de negócios. Você pode usar essas ferramentas e processos com qualquer software que você baixe do Centro de administração do Office 365 ou com a ferramenta de implantação do Office.
  
Para obter mais informações sobre como usar o Gerenciador de configuração para implantar software, consulte os seguintes artigos:
  
- [Como criar aplicativos no Configuration Manager](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Como implantar aplicativos no Gerenciador de configuração](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Se você estiver implantando o Skype para aplicativo de negócios como parte da implantação do Office 365 ProPlus, consulte [Implantar o Office 365 ProPlus, usando o System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planejamento de atualizações para o Skype para o aplicativo de negócios

Como parte da implantação do Skype para o aplicativo de negócios, você precisa considerar a como você deseja obter atualizações após a instalação do Skype para negócios. Essas atualizações podem incluir novos recursos, atualizações de segurança ou atualizações não relacionadas à segurança, como as atualizações que fornecem melhorias de desempenho ou a estabilidade. As duas coisas principais, que você precisa considerar são:
  
- Onde você deseja obter atualizações de
    
- Com que frequência você deseja obter atualizações de recurso
    
Enquanto você pode controlar onde você obter atualizações da e com que frequência você obtém atualizações de recurso, você não pode escolher quais atualizações de segurança específicos ou a você obter as atualizações não relacionadas à segurança.
  
 **Onde obter atualizações do**
  
Por padrão, após a instalação do Skype para o aplicativo de negócios, atualizações serão baixadas automaticamente da Internet quando estiverem disponíveis na Microsoft. Se você deseja ter mais controle sobre quando ocorrerem atualizações ou onde as atualizações são instaladas do, você pode usar a ferramenta de implantação do Office ou a diretiva de grupo para configurar que.
  
Por exemplo, muitas organizações desejam testar atualizações com um grupo de usuários antes de implantá-las em toda a organização. Você pode fazer isso usando a ferramenta de implantação do Office ou a diretiva de grupo para configurar o Skype para o aplicativo de negócios para obter atualizações a partir de um local específico em sua rede, em vez de automaticamente da Internet. Em seguida, você pode usar a ferramenta de implantação do Office para baixar as atualizações a cada mês em sua rede local.
  
Para obter mais informações sobre o funcionam das atualizações de software do Office 365, consulte estes artigos:
  
- [Visão geral do processo de atualização do Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Escolher como gerenciar atualizações para o Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Definir configurações de atualização do Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **A frequência de obter atualizações de recurso**
  
Além de onde você pode obter atualizações do, você pode controlar com que frequência você obtenha novos recursos para o Skype para o cliente de negócios. As duas opções são as seguintes:
  
- Obter atualizações de recurso cada mês, se houver novos recursos
    
- Obter recursos de atualizações a cada seis meses
    
Para algumas organizações, eles querem tempo para testar os novos recursos, para que eles desejam obter atualizações de recurso apenas duas vezes por ano, em vez de cada mês.
  
Você pode controlar com que frequência você obtenha atualizações de recurso usando a ferramenta de implantação do Office ou a diretiva de grupo para configurar o canal de atualização. O proporciona canal por mês você recurso atualizações mensalmente (aproximadamente), enquanto o canal anual delimitadas fornece recursos de atualizações a cada seis meses. Para obter mais informações sobre canais, consulte [Overview of canais de atualização do Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## <a name="feedback"></a>Comentários?
Para fornecer comentários sobre o produto ou para saber como estamos indo, consulte [Skype para comentários de negócios](https://www.skypefeedback.com).
