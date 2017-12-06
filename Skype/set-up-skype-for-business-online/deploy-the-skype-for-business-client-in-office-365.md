---
title: "Implantar o Cliente Skype for Business no Office 365"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- httpsfix
- LeftNav_IT_O365
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
description: "Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. "
---

# Implantar o Cliente Skype for Business no Office 365

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96). 
  
Este artigo explica as opções de como você, o **[Atribuir funções de administrador no Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, pode implantar o aplicativo Skype for Business para as pessoas em sua empresa.
  
Antes de implantar Skype for Business aos seus usuários, verifique se você já fez as etapas 1 a 3 no artigo [Configurar o Skype for Business Online](set-up-skype-for-business-online.md). Dessa maneira, Skype for Business será configurada com seu domínio, todos terão suas licenças e você será configurou mensagens Instantâneas e [Configuração de presença do Skype for Business Online](configure-presence-in-skype-for-business-online.md) para sua organização.
  
> [!NOTE]
> Para os usuários a instalar o aplicativo de Skype for Business, eles devem ser administradores locais no seu PC ou dispositivo. Ou, eles precisam ser parte de um grupo local que possa instalar aplicativos em seu computador ou dispositivos. Se os usuários não são permitidos para instalar o software em seus dispositivos, você precisará instalar o aplicativo de Skype for Business para eles. 
  
## Para a maioria das empresas de pequeno e médio porte

 **Instruções de instalação passo a passo:** Se você tiver uma empresa de pequeno ou médio porte, recomendamos que você simplesmente solicite aos usuários para instalar o aplicativo de Skype for Business em seu PC. Aponte para estas instruções:[Como instalar o Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Se elas estiverem usando Macs, aponte para [Configurar o Skype for Business (Lync) for Mac 2011 para o Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). O aplicativo de Skype for Business é instalado separadamente do restante dos aplicativos do Office.
  
 **Clientes do office 365 ProPlus:** Se sua empresa estiver usando um plano do Office 365 que inclui o Office 365 ProPlus, como o plano E3, o aplicativo de Skype for Business estiver instalado ao mesmo tempo seus usuários baixar e instalar o Word, Excel, PowerPoint, etc. Isso também significa que eles não é possível desinstalar Skype for Business, a menos que eles desinstalar todos do Office.
  
### Escolha se deseja disponibilizar o Skype for Business para os usuários

Como o [Atribuir funções de administrador no Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) que você pode optar por disponibilizar o aplicativo Skype for Business aos usuários.
  
- **Para controlar se todos na sua empresa obtém o software**: entrar para o Centro de administração do Office 365, vá para **instalar o meu software** e selecione o software que você deseja esteja disponível para usuários.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Para controlar se as pessoas específicas em sua empresa obter o software**: entrar para o Centro de administração do Office 365, vá até **usuários** > **usuários ativos**, selecione a pessoa que você deseja dar acesso ao software e clique em **Editar** ao lado de ** Licenças de produtos** e ativar ou desativar o a licença.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se você precisar ver quais planos estão atribuídos a pessoas em sua organização, entre no novo Centro de administração do Office 365 > **usuários** > **usuários ativos**. Selecione a pessoa na lista e procure em **licenças de produto**. Se você estiver usando o clássico Centro de administração do Office 365, procure em **licença atribuída**. 
  
### Implantar manualmente o Skype for Business para seus usuários
<a name="bkmk_manual_1"> </a>

Se quiser que seus usuários para instalar o aplicativo de Skype for Business de um local na sua rede, em vez da Internet, você pode baixar os arquivos de instalação. Para fazer este ir para a seção **implantar manualmente o software de usuário** da Centro de administração do Office 365. Você pode, em seguida, selecione **instalar** e salve o arquivo de .exe de instalação em um local de rede.
  
Outra opção é baixar o aplicativo básico Skype for Business para seus usuários. Você pode baixar o [Microsoft Skype for Business básico (32 ou 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Para ambos os aplicativos básicos e completos Skype for Business, depois de baixar os arquivos de instalação, você precisará enviar manualmente (por exemplo, em email) o caminho de rede para os usuários para que eles podem executar o programa de instalação para instalar o aplicativo em seu computador.
  
Você também pode usar esses downloads para implantar o aplicativo Skype for Business para seus usuários usando as ferramentas e os processos de implantação de software existentes.
  
## Para grandes organizações e empresas

> [!NOTE]
>  Esta seção aplica-se somente ao aplicativo Skype for Business disponível por meio de planos do Office 365. Se sua empresa estiver usando uma versão licenciada do volume do aplicativo Skype for Business, baseada no Windows Installer (MSI), consulte[Personalizar a instalação do cliente no Skype for Business Server 2015](https://technet.microsoft.com/pt-br/library/jj204934.aspx). 
  
Em muitos corporativo ou grandes organizações, os usuários não são permitidos para instalar o software em seus computadores. Em vez disso, os departamentos de TI implantar o software necessário para computadores dos usuários. Departamentos de TI também talvez queira controlar a quantidade de largura de banda de Internet ou rede usada em sua organização, para que eles desejam instalar o software de um local próximo em sua rede, em vez de em toda a Internet ou a rede corporativa.
  
Com o Office 365, você tem várias opções para implantar o aplicativo Skype for Business se você quiser controlar onde ele está instalado de. Algumas dessas opções incluem o seguinte:
  
- Baixe o aplicativo de Skype for Business à sua rede local da Centro de administração do Office 365, conforme descrito em [Implantando manualmente o Skype for Business para seus usuários](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#bkmk_manual).
    
- Use a **[Ferramenta de implantação do Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para baixar o Office 365 ProPlus ou o aplicativo de Skype for Business à sua rede local. Em seguida, use a ferramenta de implantação do Office para implantar o aplicativo aos usuários. A ferramenta de implantação do Office oferece a capacidade de controlar determinados aspectos da implantação, como idiomas e versão (32 bits ou 64 bits).
    
- Use seus processos, como System Center Configuration Manager e as ferramentas de implantação de software existentes para implantar o Office 365 ProPlus ou o aplicativo Skype for Business aos usuários. Você pode usar seus processos e ferramentas existentes com a [Ferramenta de implantação do Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) ou com o software que você baixou da Centro de administração do Office 365.
    
### Mais informações sobre como usar a Ferramenta de Implantação do Office

Para obter detalhes sobre como baixar a Ferramenta de Implantação do Office e muito mais informações sobre como instalar o aplicativo Skype for Business e outros aplicativos cliente do Office 365, consulte [Gerenciar o software do usuário no Office 365](https://support.office.com/article/365-c13051e6-f75c-4737-bc0d-7685dcedf360.aspx).
  
Aqui está uma visão geral das etapas envolvidas no uso a ferramenta de implantação do Office para implantar um aplicativo:
  
1. **[Baixe a ferramenta de implantação mais recente do Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** da Microsoft Download Center.
    
2. Criar o arquivo configuration.xml para ser usado com a Ferramenta de Implantação do Office que tem as configurações ao aplicativo cliente que você deseja, como a configuração da versão (32 bits ou 64 bits), o idioma da instalação, etc.
    
3. Use a ferramenta de implantação do Office e o arquivo Configuration para baixar os arquivos de instalação para sua rede interna ou local de rede de entrega conteúdo do Office (CDN).
    
4. Use a ferramenta de implantação do Office e o Configuration para instalar os aplicativos de cliente do Office, inclusive o aplicativo Skype for Business.
    
Para obter detalhes sobre a utilização da Ferramenta de Implantação do Office e do arquivo configuration.xml, consulte os seguintes artigos:
  
- [Visão geral da Ferramenta de Implantação do Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configurações do arquivo configuration.xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### Mais informações sobre como usar o Gerenciador de configuração do System Center

Você pode usar seu ferramentas de implantação de software existentes e processos, como o System Center Configuration Manager, para implantar o aplicativo Skype for Business. Você pode usar essas ferramentas e processos com o software que você baixar da Centro de administração do Office 365 ou com a ferramenta de implantação do Office.
  
Para obter mais informações sobre como usar o Gerenciador de configuração para implantar o software, consulte os seguintes artigos:
  
- [Como criar aplicativos no Gerenciador de Configuração](https://technet.microsoft.com/pt-br/library/gg682159.aspx)
    
- [Como implantar aplicativos no Gerenciador de Configuração](https://technet.microsoft.com/pt-br/library/gg682082.aspx)
    
Se você estiver implantando o aplicativo Skype for Business como parte da implantação do Office 365 ProPlus, consulte [Implantar o Office 365 ProPlus usando o Gerenciador de configuração do sistema central](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## Planejamento de atualizações para o aplicativo Skype for Business

Como parte da implantação do aplicativo Skype for Business, você precisa considerar como você deseja obter atualizações após a instalação do Skype for Business. Essas atualizações podem incluir novos recursos, atualizações de segurança ou atualizações não são de segurança, como as atualizações que fornecem melhorias de desempenho ou de estabilidade. As duas coisas principais, que você precisa considerar são:
  
- Onde você deseja obter atualizações do
    
- Com que frequência você deseja obter atualizações do recurso
    
Enquanto você pode controlar onde obter atualizações do e com que frequência você receberá atualizações de recursos, você não pode escolher quais atualizações de segurança específicas ou atualizações de segurança não receber.
  
 **De onde obter atualizações**
  
Por padrão, depois de instalar o aplicativo de Skype for Business, as atualizações serão baixadas automaticamente da Internet quando eles estão disponíveis na Microsoft. Se desejar mais controle sobre quando ocorrerem atualizações ou onde as atualizações são instaladas do, você pode usar a ferramenta de implantação do Office ou a política de grupo para configurar esse.
  
Por exemplo, muitas organizações desejam testar atualizações com um grupo de usuários antes de implantá-las em toda a organização. Você pode fazer isso usando a ferramenta de implantação do Office ou a política de grupo para configurar o aplicativo de Skype for Business para obter atualizações de um local específico em sua rede, em vez de automaticamente da Internet. Em seguida, você pode usar a ferramenta de implantação do Office para baixar as atualizações de cada mês para sua rede local.
  
Para obter mais informações sobre como funcionam as atualizações de software do Office 365, consulte estes artigos:
  
- [Visão geral do processo de atualização para o Office 365 ProPlus](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Escolher como gerenciar atualizações do Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configurar definições de atualização para o Office 365 ProPlus](https://technet.microsoft.com/pt-br/library/dn761708.aspx)
    
 **Com que frequência receber as atualizações de recursos**
  
Além de onde obter as atualizações do, você também pode controlar com que frequência você obter novos recursos para o Skype for Business client. As duas opções são as seguintes:
  
- Obter atualizações de recursos todo mês, se há novos recursos
    
- Obter atualizações de recursos a cada seis meses
    
Para algumas organizações, desejam tempo para testar novos recursos, para que eles desejam obter atualizações de recursos somente duas vezes por ano em vez de cada mês.
  
Você pode controlar com que frequência você obter atualizações do recurso usando a ferramenta de implantação do Office ou a política de grupo para configurar o canal de atualização. O oferece mensal canal você recurso atualizações mensais (aproximadamente), enquanto o canal de ponto anual oferece recurso atualizações a cada seis meses. Para obter mais informações sobre canais, consulte [Visão geral de canais de atualização para o Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## Tópicos Relacionados

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)
  
[Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

