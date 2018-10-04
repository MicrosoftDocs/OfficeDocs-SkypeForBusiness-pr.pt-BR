---
title: Atualização do Gerenciador de estatísticas do Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumo: Leia este tópico para saber como atualizar o Gerenciador de estatísticas Skype for Business Server 2015.'
ms.openlocfilehash: d10dd5cd92fc0d7dbbb3285c43df78e8149f58c0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374854"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a>Atualização do Gerenciador de estatísticas do Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como atualizar o Gerenciador de estatísticas Skype for Business Server 2015.
  
Este tópico descreve como atualizar uma instalação existente do Gerenciador de estatísticas Skype for Business Server — uma ferramenta poderosa que permite que você visualize Skype para dados de integridade e desempenho do servidor de negócios em tempo real. Você pode sondar dados de desempenho em centenas de servidores por cada alguns segundos e exiba os resultados instantaneamente no site do Gerenciador de estatísticas. 
  
Para obter mais informações sobre o Gerenciador de estatísticas e os novos recursos na versão 1.1, consulte [Planejar para o Gerenciador de estatísticas de Skype para Business Server 2015](plan.md) e o [Gerente estatísticas implantar Skype para Business Server 2015](deploy.md). Para obter informações sobre problemas conhecidos corrigidos na versão 1.1, veja [Problemas conhecidos corrigidos na versão 1.1](upgrade.md#BKMK_Fixed).
  
Existem dois métodos para a atualização:
  
- **Atualização automatizada.** Este método usa um script automatizado. É o método mais fácil e deve ser aplicável a todos os cenários de atualização.
    
- **Atualização manual.** Este método é fornecido como um plano de backup no caso incomum que está falhando a atualização automatizada.
    
## <a name="prerequisites"></a>Pré-requisitos

Antes de atualizar, certifique-se de ter as seguintes informações:
  
- Impressão digital do certificado do Ouvinte ativo
    
- Senha de serviço do Ouvinte (inserida na instalação do Ouvinte e de cada Agente)
    
- Configuração de Certificado SSL do site da Web
    
## <a name="automated-upgrade"></a>Atualização automatizada

O script reunirá suas informações de certificado e senha do ouvinte atuais, desinstalará a versão antiga do produto e, em seguida, instalará a nova versão. A instância do Redis instalada no servidor não será alterada, portanto, todos os dados armazenados no cache serão retidos no processo de atualização.
  
1. Coloque os arquivos MSI da nova versão do agente, ouvinte e site juntamente com o script StatsMan.ps1 de atualização em uma única pasta no computador ouvinte.
    
2. Abra uma janela de administrador do PowerShell. Atualize o componente do Ouvinte:
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> A senha do serviço Gerenciador de estatísticas será exibida em texto não criptografado na linha de comando conforme ele é passado para o instalador. Proteja seu monitor conforme necessário. 
  
1. Na execução do script, você será solicitado a desinstalar a versão antiga do produto. Responda Sim.
    
2. Se o serviço Ouvinte estiver em operação, você será solicitado a fechar o aplicativo antes de continuar. Permitir que o aplicativo fechar (o ouvinte do Gerenciador de estatísticas serviço será interrompido).
    
3. Continue o processo de instalação. Você notará que a senha de serviço e a impressão digital do certificado são pré-preenchidos. Se não forem, adicione os valores salvos antes de continuar.
    
4. Abra uma janela de administrador do PowerShell. Atualize o componente do site:
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Na execução do script, você será solicitado a desinstalar a versão antiga do produto. Responda Sim.
    
6. Se o serviço do Agente estiver em operação, você será solicitado a fechar o aplicativo antes de continuar. Permita que o aplicativo seja fechado (o serviço do Agente StatsMan será interrompido).
    
7. Continue o processo de instalação. Você notará que a senha de serviço e a impressão digital do certificado são pré-preenchidos. Se não forem, adicione os valores salvos antes de continuar.
    
8. Abra uma janela de administrador do PowerShell. Atualize o componente do Agente:
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Na execução do script, você será solicitado a desinstalar a versão antiga do produto. Responda Sim.
    
10. Continue o processo de instalação. Você notará que a porta do site é pré-preenchida. Se não for, adicione o valor salvo antes de continuar.
    
11. Verifique se o site está funcionando conforme esperado usando o navegador.
    
> [!NOTE]
> A atualização do Agente pode ser usada com o comutador -NoPrompt. Isso permitirá que o processo de desinstalação/instalação seja executado silenciosamente, permitindo que ferramentas como PSExec sejam executadas remotamente durante a atualização em vários servidores. 
  
### <a name="manual-upgrade"></a>Atualização manual

Se, por algum motivo, a atualização automatizada falhar, é possível executar uma atualização manual da seguinte maneira:
  
1. 	No computador Ouvinte, desinstale o Ouvinte, o Site e o Agente (se instalados no servidor) através do painel de controle Programas e Recursos.   
    
    > [!NOTE]
    >   Mantenha o Redis instalado para que os dados no cache sejam mantidos durante o processo de atualização.
  
2. 	Instale as novas versões dos componentes, incluindo os valores salvos acima quando solicitados. Para obter mais informações sobre como instalar componentes, veja [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy)
    
## <a name="known-issues-fixed-in-release-11"></a>Problemas conhecidos corrigidos na versão 1.1
<a name="BKMK_Fixed"> </a>

Os seguintes problemas conhecidos foram corrigidos na versão 1.1:
  
- Interface do usuário/Server/Agent - diversas melhorias no desempenho e confiabilidade significativa
    
- Interface do usuário - controle de filtro principal agora classificará corretamente com diferentes casos (foi gerando pessoas pensar determinados servidores não estavam no sistema quando fossem)
    
- Servidor - Os componentes de servidor agora serão instalados em servidores que não estiverem em inglês.
    
- Servidor/Agente - Em alguns casos, os componentes de agente e servidor não eram instalados, com erros .NET devido a uma versão específica do .NET 4.0. Isso foi resolvido.
    
- Agente - estendido adicionado para o agente de StatsMan do log de eventos. O agente não travará mais quando instalado em um servidor que não está na topologia, isso agora é registrado no log de eventos, junto com muitas outras possíveis condições de erro.
    
- Interface do usuário - clientes Web usando o navegador Chrome veria vários prompts de logon quando usando um computador cliente não ingressou no mesmo grupo de trabalho ou domínio como o servidor Web do Gerenciador de estatísticas. Agora, apenas um único logon deve ser exigido por sessão.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Fixed"> </a>

Para obter mais informações, consulte:
  
- [Planejar para o Gerenciador de estatísticas de Skype Business Server 2015](plan.md)
    
- [Implantar o Gerenciador de Estatísticas para o Skype for Business Server 2015](deploy.md)
    
- [Solução de problemas do Gerenciador de estatísticas do Skype for Business Server 2015](troubleshoot.md)
    
- [Skype para o blog do Gerenciador de estatísticas do servidor de negócios](https://blogs.technet.microsoft.com/skypestatsman/)
    

