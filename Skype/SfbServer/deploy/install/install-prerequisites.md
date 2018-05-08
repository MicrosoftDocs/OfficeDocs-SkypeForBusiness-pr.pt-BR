---
title: Instalar os pré-requisitos para o Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumo: Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar Skype para Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6d11b83cf760b47072bca743b6fe3b5fac3794d9
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Instalar os pré-requisitos para o Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar Skype para Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Os pré-requisitos de instalação consistem na configuração do Windows Server por meio da instalação das funções e dos recursos necessários em cada servidor da topologia. Os requisitos são baseados na função que o servidor vai desempenhar na topologia. Você pode executar os passos 1 a 5 em qualquer ordem. No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. Os pré-requisitos de instalação é a etapa 1 de 8.
  
![Diagrama de visão geral - instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Instalação do Windows Server

Skype para Business Server 2015 requer o sistema operacional Windows Server e um número de pré-requisitos antes que ele possa ser instalado. Para obter detalhes sobre como planejar os pré-requisitos, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Esse procedimento usa o Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser um pouco diferente. 
  
> [!IMPORTANT]
> Antes de começar, certifique-se de que o Windows Server seja atualizada usando o Windows Update. 
  
![Windows Server atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Assista as etapas do vídeo para **os pré-requisitos de instalação**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instale as funções e os recursos necessários para os servidores front-end

1. Abra o Server Manager e clique em **Adicionar funções e recurso**.
    
2. Leia a página **Antes de Começar** para se familiarizar com a instalação de funções e recursos no Windows Server, e depois clique em **Avançar**.
    
3. Selecione **Instalação baseada em função ou baseada em recurso**, e clique em **Avançar**.
    
4. Selecione o servidor no qual você será instalando Skype para Business Server 2015 e clique em **Avançar**.
    
5. Selecione a função **Servidor Web (IIS)**, e quando a janela de recursos obrigatórios aparecer, clique em **Adicionar recursos**, e depois clique em **Avançar**.
    
6. Verifique se os recursos de software listados no [Software que deve ser instalado antes de um Skype para implantação Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) estão no servidor que executará o Skype para Business Server 2015. Aqui está uma lista resumida:
    
   - Recursos do .NET framework
    
   - Recursos do WCF
    
   - Ativação HTTP
    
    > [!NOTE]
    > A Ativação HTTP requer recursos adicionais. Clique em **Adicionar recursos** para ver a caixa de diálogo que aparecerá quando você selecionar Ativação HTTP.
  
   - Media Foundation (necessário para servidores Front-End e servidores Standard Edition usadas para conferências).
    
   - AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto
    
   - Ferramentas de Administração de Funções
    
   - AD DS 
    
   - O AD LDS
    
   - Windows Identity Foundation 3.5
    
7. Clique em **Avançar** para continuar no assistente.
    
8. Leia as observações sobre a **Função Servidor Web (IIS)**, e depois clique em **Avançar**.
    
9. Selecione os seguintes **serviços de função Servidor Web (IIS)**.
    
   - Recursos HTTP Comuns
    
   - Documento padrão
    
   - Pesquisa de diretório
    
   - Erros HTTP
    
   - Conteúdo estático
    
   - Integridade e Diagnósticos
    
   - Log HTTP
    
   - Ferramentas de log
    
   - Rastreamento
    
   - Desempenho
    
   - Compressão de conteúdo estático
    
   - Compactação de conteúdo dinâmico
    
   - Segurança
    
   - Requisição de filtro
    
   - Autenticação de mapeamento de certificado de cliente
    
   - Autenticação do Windows
    
   - Desenvolvimento do aplicativo
    
   - Extensibilidade .NET 3.5
    
   - Extensibilidade .NET 4.5
    
   - ASP.NET 3.5
    
   - ASP.NET 4.5
    
   - Extensões ISAPI
    
   - Filtros ISAPI
    
   - Ferramentas de gerenciamento
    
   - Console de gerenciamento IIS
    
   - Ferramentas e scripts de gerenciamento IIS
    
10. Clique em **Avançar** para continuar no assistente.
    
11. Examine as seleções de instalação para certificar-se de que todos os requisitos foram selecionados e clique em **Instalar**.
    
    > [!CAUTION]
    > O Windows Server 2012 R2 não instala todos os arquivo de origem para os recursos necessários por padrão. Se o servidor não estiver conectado à Internet, você terá que inserir a mídia do Windows Server 2012 R2 e selecionar **Especificar um caminho de origem alternativo** para instalar os recursos necessários. Os arquivos de origem estão localizados no diretório sources\sxs. Por exemplo, se a mídia do Windows Server 2012 R2 estiver na unidade D, você teria que definir o caminho como `d:\sources\sxs`. > É importante que você tenha as atualizações mais recentes do Windows Update. Se você não estiver conectado à Internet, terá que instalar manualmente todas as atualizações importantes, bem como quaisquer pré-requisitos para as atualizações necessárias. 
  
12. Quando a caixa de diálogo indicar que a instalação foi concluída, você terá que reiniciar o servidor para concluir o processo.
    
13. Execute o **Windows Update** novamente para verificar se há alguma atualização para as funções e os serviços que foram instalados.
    
14. Se você for usar Skype para painel de controle do Business Server neste servidor você também deve instalar o Silverlight. Para instalar o Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).
    
Os pré-requisitos podem ser instalados executando o seguinte comando PowerShell. Observe que o comando procura arquivos de origem em uma ordem específica. Se você estiver online, o comando acessa o Windows Update. No entanto, se você estiver offline, terá que verificar se os arquivos de origem estão disponíveis para o comando. Para obter mais informações sobre como usar o PowerShell para instalar as funções e recursos, consulte [instalar ou desinstalar funções, serviços de função ou recursos](https://technet.microsoft.com/en-us/library/hh831809.aspx) e [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx). Não se esqueça de executar o Windows Update novamente após instalar os pré-requisitos, mesmo se você usar o comando PowerShell.
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> Os pré-requisitos para servidores executando funções diferentes da de servidor front-end, como a função de Diretor, Chat Persistente ou Borda, terão seus próprios pré-requisitos. Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

