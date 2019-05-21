---
title: Atualizar o Gerenciador de estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumo: Leia este tópico para saber como atualizar o Gerenciador de estatísticas do Skype for Business Server.'
ms.openlocfilehash: 70826776e9dfacdef75c7084a9aba6f4eede940a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299720"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Atualizar o Gerenciador de estatísticas do Skype for Business Server
 
**Resumo:** Leia este tópico para saber como atualizar o Gerenciador de estatísticas do Skype for Business Server.
  
Este tópico descreve como atualizar uma instalação existente do Gerenciador de estatísticas do Skype for Business Server, uma ferramenta poderosa que permite que você visualize dados de integridade e desempenho do Skype for Business Server em tempo real. É possível sondar dados de desempenho em centenas de servidores em intervalos de alguns segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas. 
  
Para obter mais informações sobre o Gerenciador de estatísticas e os novos recursos no lançamento 2,0, consulte [planejar o Gerenciador de estatísticas para o Skype for Business Server](plan.md) e [implantar o Gerenciador de estatísticas para o Skype for Business Server](deploy.md).
  
Existem dois métodos para a atualização:
  
- **Atualização automatizada.** Esse método usa um script automatizado. É o método mais fácil e deve ser aplicado a todos os cenários de atualização.
    
- **Atualização manual.** Esse método é fornecido como um plano de backup no caso incomum de a atualização automatizada falhar.
    
## <a name="prerequisites"></a>Pré-requisitos

Antes de atualizar, certifique-se de ter as seguintes informações:
  
- Impressão digital do certificado do Ouvinte ativo
    
- Senha de serviço do Ouvinte (inserida na instalação do Ouvinte e de cada Agente)
    
- Configuração de Certificado SSL do site da Web
    
## <a name="automated-upgrade"></a>Atualização automatizada

O script reunirá suas informações de certificado e senha do ouvinte atuais, desinstalará a versão antiga do produto e, em seguida, instalará a nova versão. A instância do Redis instalada no servidor não será alterada, portanto, todos os dados armazenados no cache serão retidos no processo de atualização.
  
1. Coloque os arquivos MSI da nova versão do agente, ouvinte e website juntamente com o script Update-StatsMan. ps1 em uma única pasta no computador ouvinte.
    
2. Abra uma janela de administrador do PowerShell. Atualize o componente do Ouvinte:
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> A senha do serviço do Gerenciador de estatísticas será exibida em texto não criptografado na linha de comando conforme ela é passada para o instalador. Proteja seu monitor conforme necessário. 
  
1. Na execução do script, você será solicitado a desinstalar a versão antiga do produto. Responda Sim.
    
2. Se o serviço Ouvinte estiver em operação, você será solicitado a fechar o aplicativo antes de continuar. Permita que o aplicativo seja fechado (o serviço de escuta do Gerenciador de estatísticas será interrompido).
    
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

    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Fixed"> </a>

Para obter mais informações, consulte o seguinte:
  
- [Planejar o Gerenciador de estatísticas do Skype for Business Server](plan.md)
    
- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)
    
- [Solução de problemas do Gerenciador de estatísticas do Skype for Business Server](troubleshoot.md)
