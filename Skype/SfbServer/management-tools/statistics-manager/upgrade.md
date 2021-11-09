---
title: Atualizar o Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumo: leia este tópico para saber como atualizar o Gerenciador de Estatísticas para Skype for Business Server.'
ms.openlocfilehash: 297da8efc1259c1128fd0d60584e1db761465217
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857328"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Atualizar o Gerenciador de Estatísticas do Skype for Business Server
 
**Resumo:** Leia este tópico para saber como atualizar o Gerenciador de Estatísticas para Skype for Business Server.
  
Este tópico descreve como atualizar uma instalação existente do Gerenciador de Estatísticas para Skype for Business Server — uma ferramenta poderosa que permite exibir dados de Skype for Business Server e desempenho em tempo real. Você pode sondar dados de desempenho em centenas de servidores a cada poucos segundos e exibir os resultados instantaneamente no Site do Gerenciador de Estatísticas. 
  
Para obter mais informações sobre o Gerenciador de Estatísticas e os novos recursos na Versão 2.0, consulte [Plan for Statistics Manager for Skype for Business Server](plan.md) and Deploy [Statistics Manager for Skype for Business Server](deploy.md).
  
Há dois métodos para atualização:
  
- **Atualização automatizada.** Esse método usa um script automatizado. É o método mais fácil e deve ser aplicável a todos os cenários de atualização.
    
- **Atualização manual.** Esse método é fornecido como um plano de backup no caso incomum de falha na atualização automatizada.
    
## <a name="prerequisites"></a>Pré-requisitos

Antes de atualizar, certifique-se de ter as seguintes informações:
  
- Impressão digital do Certificado do Ouvinte Ativo
    
- Senha do Serviço de Ouvinte (inserida na instalação do ouvinte e de cada agente)
    
- Configuração do certificado SSL para o site
    
## <a name="automated-upgrade"></a>Atualização automatizada

O script coletará suas informações de certificado atual e senha de ouvinte, desinstalará a versão antiga do produto e instalará a nova versão do produto. A instância Redis instalada no servidor não será tocada, portanto, todos os dados armazenados no cache serão mantidos por meio do processo de atualização.
  
1. Coloque os arquivos MSI para a nova versão do agente, ouvinte e site juntamente com o script Update-StatsMan.ps1 em uma única pasta no computador Ouvinte.
    
2. Abra uma janela administrativa do PowerShell. Atualize o componente Ouvinte:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> A senha de serviço do Gerenciador de Estatísticas será exibida em texto claro na linha de comando à medida que ela for passada para o instalador. Certifique-se de proteger o monitor conforme necessário. 
  
1. Ao executar o script, você deve ser solicitado a desinstalar a versão antiga do produto. Resposta Sim.
    
2. Se o serviço Ouvinte estiver em execução, você será solicitado a fechar o aplicativo antes de continuar. Permitir que o aplicativo feche (o serviço Ouvinte do Gerenciador de Estatísticas será interrompido).
    
3. Continue o processo de instalação. Você deve observar que a senha de serviço e a impressão digital do certificado estão pré-preenchidas. Se não, adicione os valores salvos antes de continuar.
    
4. Abra uma janela administrativa do PowerShell. Atualize o componente site:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Ao executar o script, você deve ser solicitado a desinstalar a versão antiga do produto. Resposta Sim.
    
6. Se o serviço agente estiver em execução, você será solicitado a fechar o aplicativo antes de continuar. Permitir que o aplicativo feche (o serviço Agente StatsMan será interrompido).
    
7. Continue o processo de instalação. Você deve observar que a senha de serviço e a impressão digital do certificado estão pré-preenchidas. Se não, adicione os valores salvos antes de continuar.
    
8. Abra uma janela administrativa do PowerShell. Atualize o componente do Agente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Ao executar o script, você deve ser solicitado a desinstalar a versão antiga do produto. Resposta Sim.
    
10. Continue o processo de instalação. Você deve observar que a porta do site está pré-preenchida. Se não, adicione o valor salvo antes de continuar.
    
11. Verifique se o site está funcionando conforme o esperado usando o navegador.
    
> [!NOTE]
> A atualização do Agente pode ser usada com a opção -NoPrompt. Isso permitirá que o processo de desinstalação/instalação seja executado silenciosamente, permitindo que ferramentas como o PSExec executem a atualização remotamente em um grande número de servidores. 
  
### <a name="manual-upgrade"></a>Atualização manual

Se, por algum motivo, a atualização automatizada falhar, você sempre poderá executar uma atualização manual da seguinte forma:
  
1. No computador Ouvinte, desinstale o Ouvinte, o Site e o Agente (se ele foi instalado neste servidor) por meio do painel de controle Programas e Recursos. 
    
    > [!NOTE]
    >  Mantenha Redis instalado para que os dados no cache sejam mantidos por meio do processo de atualização.
  
2. Instale as novas versões dos componentes, incluindo os valores que você salvou acima quando solicitado a eles. Para obter mais informações sobre a instalação de componentes, consulte [Deploy Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Fixed"> </a>

Para obter mais informações, confira o seguinte:
  
- [Planejar o Gerenciador de estatísticas do Skype for Business Server](plan.md)
    
- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)
    
- [Solução de problemas do Gerenciador de estatísticas do Skype for Business Server](troubleshoot.md)
