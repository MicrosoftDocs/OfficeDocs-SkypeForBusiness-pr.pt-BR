---
title: Solução de problemas do Gerenciador de estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumo: Leia este tópico para solucionar problemas de implantação do Gerenciador de estatísticas do Skype for Business Server.'
ms.openlocfilehash: 7d9ea061453998f2df01cd2ec31e792600697ee1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992508"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Solução de problemas do Gerenciador de estatísticas do Skype for Business Server
 
**Resumo:** Leia este tópico para solucionar problemas de implantação do Gerenciador de estatísticas do Skype for Business Server.
  
Este tópico descreve como solucionar problemas de implantação do Gerenciador de estatísticas descrevendo os eventos que podem ser exibidos no log de eventos do aplicativo e as ações adequadas que você pode tomar para retificar o evento. Este tópico contém as seguintes seções:
  
- [Eventos do Agente](troubleshoot.md#BKMK_Agent)
    
- [Eventos do Ouvinte](troubleshoot.md#BKMK_Listener)
    
- [Problemas de site da Web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventos do Agente
<a name="BKMK_Agent"> </a>

- **1000** - Não é possível instalar o limitador do processador (Objeto de trabalho) - Motivo desconhecido
    
- **1001** – a limitação de processo não é permitida no processo (provavelmente já dentro de um objeto de trabalho)
    
    O Agente é executado dentro de um Objeto de trabalho do Windows que limita automaticamente seu volume de memória. Se o agente não for iniciado e essas entradas de evento estiverem presentes no log de eventos, o Objeto de trabalho não consegue ser instanciado no servidor. Para contornar o problema, o limite de memória superior pode ser removido com a alteração de um valor no arquivo de configurações:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Procure por "MaxProcessMemoryMB" e altere o valor para "0" conforme mostrado:
    
  ```console
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se essa alteração for feita, o agente geralmente ainda consumirá \< 100 MB de memória, mas ele não se limitará à força a 300 MB, como é o padrão. Se essa alteração for feita, recomendamos monitorar de perto uso de memória para garantir que o Agente não consuma uma grande quantidade de memória na máquina do host. 
  
- **2000** - Falha na inicialização do cliente
    
- **2001** - Não foi possível se conectar com o serviço em qualquer IP de origem
    
    Se o Agente não puder se conectar ao computador Ouvinte, verifique o seguinte:
    
1. Certifique-se de que o serviço Ouvinte está em execução no computador Ouvinte. Se não estiver, certifique-se de que o Redis está sendo executado no servidor e reinicie o serviço Ouvinte.
    
    Verifique o log de eventos do Gerenciador de estatísticas no computador ouvinte para garantir que não haja problemas com o serviço de escuta do Gerenciador de estatísticas propriamente dito.
    
2. Use uma ferramenta de conectividade, como telnet, para verificar a conectividade do computador do Agente ao do Ouvinte na porta correta.
    
    Caso contrário, verifique se a regra de firewall de entrada está habilitada no computador Ouvinte para o tipo de rede ao qual esse computador está conectado (público/privado/domínio). Se o computador ouvinte não estiver associado a um domínio, a rede poderá estar listada como pública e, nesse caso, as regras de firewall instaladas com o Gerenciador de estatísticas não serão aplicadas por padrão.
    
- **4000** - Falha para no download das Informações do servidor do Ouvinte (Motivo desconhecido)
    
  - **4001** - Servidor não encontrado na topologia do Ouvinte
    
    Esse erro ocorrerá se o servidor se conectar com êxito ao ouvinte, mas o servidor não tiver sido adicionado à topologia no cache do ouvinte. Opções de solução:
    
  - 	Certifique-se de seguir as instruções para importar a topologia. Veja [Importar a topologia](deploy.md#BKMK_ImportTopology).   
    
  - Se o Agente estiver em um servidor que não está listado na topologia (por exemplo, os nós de um cluster SQL AlwaysOn), você precisará adicionar o Agente manualmente seguindo as instruções contidas em [Importar a topologia](deploy.md#BKMK_ImportTopology).
    
  - **4002** - Senha do Ouvinte inválida
    
    A senha codificada que o agente esteja tentando usar não corresponde à senha de serviço no Ouvinte. Desinstale o Agente e volte a instalá-lo usando a senha de serviço correta.
    
  - **4003** - Incompatibilidade de impressão digital do certificado
    
    A impressão digital do certificado dada ao Agente durante a instalação não corresponde à impressão digital no certificado que o Ouvinte está usando no momento e, portanto, a conexão será recusada. Desinstale o Agente e volte a instalá-lo usando a impressão digital do certificado correta.
    
  - **4004** - Resposta inválida ou HttpStatusCode
    
    O Ouvinte não está respondendo com um status esperado.   
    
  - Se a conexão for em proxy, marque a configuração de proxy.
    
  - Verifique se há problemas com a configuração no log do estado do estado do ouvinte do computador.
    
  - **4005** - Não foi possível desserializar o XML
    
    As informações no servidor do Ouvinte estão corrompidas ou pode haver uma incompatibilidade de versões entre os computadores do Agente e do Ouvinte. Certifique-se de que as versões são as mesmas e verifique o log de eventos do Ouvinte em busca de problemas.
    
## <a name="listener-events"></a>Eventos do Ouvinte
<a name="BKMK_Listener"> </a>

- **10000** - Falha na inicialização Motivo desconhecido (são irrecuperáveis, e o serviço será interrompido/falhará como resultado)
    
  - **10001** - Problema de configuração
    
    Isso geralmente ocorre quando o arquivo [listener_install_location]\PerfAgentListener.exe.config foi modificado manualmente e não pode ser lido pelo aplicativo.
    
  - **10002** - Erro de inicialização do Ouvinte do HTTP
    
    Esse evento geralmente será registrado quando a ACL da URL não tiver sido definida adequadamente durante a instalação ou o certificado SSL é inválido. Verifique se o certificado em sua configuração é válido. Se for, reinstale o Ouvinte seguindo as instruções contidas em [Implantar o Gerenciador de Estatísticas](deploy.md#BKMK_Deploy).
    
  - **10003** - Falha de Redis
    
  - **10004** - Falha na infraestrutura do cache
    
  - **10007** - Configurações (armazenadas em Redis)
    
    O Ouvinte não conseguiu contatar o Redis ou recuperar dados bem formados do cache, e não foi possível iniciar. Certifique-se de que o serviço Redis foi iniciado e configurado adequadamente no servidor.
    
  - **10005** - Recuperação/análise das informações do servidor
    
    As informações de topologia no cache Redis são inválidas. Primeiro, tente reiniciar Redis e o Ouvinte. Se o erro persistir, veja [Importar a topologia](deploy.md#BKMK_ImportTopology) para recriar os dados da topologia.
    
- **10100** - Interrupção de PING do Redis
    
  - **10101** - Interrupção continuada de PING do Redis (a cada 60 segundos)
    
  - **30100** - Interrupção de PING do Redis restaurada
    
    Esses eventos serão registrados quando o Ouvinte não puder se conectar ao Redis. Verifique se o Redis foi iniciado e a conectividade de rede entre o Ouvinte e o Redis está disponível.
    
- **10200** - Interrupção de gravação do Redis
    
  - **10201** - Interrupção continuada de gravação do Redis (a cada 60 segundos)
    
  - **30100** - Interrupção de gravação do Redis resolvida
    
    Esses eventos serão registrados quando o Ouvinte não puder gravar no cache do Redis. Verifique se o Redis foi iniciado e a conectividade de rede entre o Ouvinte e o Redis está disponível.
    
- **30000** - Iniciado com êxito
    
    Registrado toda vez que o Ouvinte é iniciado.
    
- **22000** – inicialização do agente do Gerenciador de estatísticas bem-sucedida.
    
- **23000** - Inicialização bem-sucedida do EventLogQueryManager (primeira vez ou após uma falha)
    
- **24000** - Inicialização bem-sucedida de serverinfo (primeira vez ou após uma falha)
    
- **25000** - O Ouvinte está online novamente após uma falha ao postar (ou primeira postagem bem-sucedida)
    
- **5000** - Início do ouvinte offline para postagem de dados
    
- **5001** - O Ouvinte continua offline durante um período extenso
    
    Esses eventos podem ser úteis para monitorar/alertar sobre/resolver problemas.
    
## <a name="website-issues"></a>Problemas de site da Web
<a name="BKMK_Website"> </a>

- Prompts de login repetitivo no Chrome-foi um bug que foi resolvido na versão 1,1. Verifique se você atualizou para a versão mais recente do Gerenciador de estatísticas se estiver vendo solicitações de login repetidas no navegador Chrome. Para conferir a versão do site executada:
    
  - 	No Explorador de Arquivos, abra (default directory)
    
  - Clique com o botão direito do mouse em StatsManHubWebSite.dll e veja as propriedades.
    
  - Caso um computador não possa ser encontrado no modo de exibição Paisagem do KHI ou no modo de exibição Detalhes do Contador, verifique se ele é membro de um Site e de um Pool. Se não for, ele não aparecerá nesses modos de exibição. Para obter informações sobre como definir um site e um pool para um servidor na topologia, veja [Importar a topologia](deploy.md#BKMK_ImportTopology).
    
  - A versão do produto será mostrada nos detalhes de Descrição.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_Website"> </a>

Para obter mais informações, consulte o seguinte:
  
- [Planejar o Gerenciador de estatísticas do Skype for Business Server](plan.md)
    
- [Implantar o Gerenciador de estatísticas do Skype for Business Server](deploy.md)
    
- [Atualizar o Gerenciador de estatísticas do Skype for Business Server](upgrade.md)
