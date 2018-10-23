---
title: Implantar o Lync VDI plug-in com Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: krishra
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Este tópico aborda os procedimentos de implantação para uso do Skype for Business durante a conexão a uma área de trabalho remota virtual.
ms.openlocfilehash: 792e6ab2521be2eaf46bc3a43979173d878fcb63
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699690"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Implantar o Lync VDI plug-in com Skype para Business Server
 
Este tópico aborda os procedimentos de implantação para uso do Skype for Business durante a conexão a uma área de trabalho remota virtual. Considerações de planejamento correm [Planejar Skype para os negócios em ambientes de VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações nas quais questões de segurança e conformidade são especialmente sensíveis. Seus usuários trabalham em computadores Windows locais e utilizam clientes em uma área de trabalho virtual. Usando Skype para a empresa em uma conexão como esta requer o software de plug-in de VDI adicional.
  
Existem duas soluções disponíveis para o componente de plug-in de VDI - uma oferecida pela Microsoft e outro oferecidos pelo Citrix. A Microsoft recomenda usar a nova solução de pacote de otimização do HDX em tempo real em novas implantações, mas continuará a dar suporte a plug-in VDI do Lync original para o restante do seu ciclo de vida. 
  
Este tópico fornece detalhes sobre como implantar o Microsoft Lync VDI plug-in, que só tem suporte no Windows 7 e Windows 8 ou Windows Server 2008 e suporta apenas o Lync 2013 ou Skype para clientes corporativos. Não existem planos para atualizar este plug-in, mas o [Pacote de otimização do Citrix HDX em tempo real](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) para Skype para negócios serão atualizados conforme necessário.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Preparar seu ambiente para o plug-in VDI do Lync
<a name="Prepare_vdi"> </a>

1. No Skype para Business Server, certifique-se de que o EnableMediaRedirection está definido como TRUE para todos os usuários de plug-in Lync VDI. Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e o cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. No servidor do Centro de dados, instale o Skype para o cliente de negócios em todas as áreas de trabalho virtuais.
    
3. Nos computadores locais, instale o plug-in Lync VDI.
    
    Os usuários agora devem conectar um dispositivo, como um fone de ouvido com microfone ou uma webcam, ao computador local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Definir as configurações da Conexão de Área de Trabalho Remota
<a name="Prepare_vdi"> </a>

Para preparar a Conexão de área de trabalho remota para o Lync VDI plug-in, siga estas etapas no computador local:
  
1. Se o computador local estiver executando o Windows 8, ignore esta etapa. Se o computador local executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do [cliente de serviços de área de trabalho remota](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
2. Inicie o cliente de Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão de Área de Trabalho Remota**.
    
3. Clique em **Opções**.
    
4. Clique na guia **Recursos Locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:
    
   - Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.
    
   - Em **Gravação de áudio remoto**, selecione **Não gravar**.
    
   - Clique em **OK**.
    
5. Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Armazenamento persistente de bitmaps em cache**.
    
6. Clique na guia **Geral**. Em **Computador**, digite o nome da área de trabalho virtual e clique em **Conectar**.  
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Entrar e usar o Skype for Business na área de trabalho virtual
<a name="SfB_signin"> </a>

Depois que o Lync VDI plug-in estiver habilitado, o usuário segue estas etapas ao entrar no Skype para negócios na área de trabalho virtual.
  
1. O usuário digita suas credenciais para o Skype para cliente corporativos em execução na área de trabalho virtual.
    
2. Depois Skype para negócios detecta o plug-in Lync VDI, Skype para negócios solicita ao usuário inserir novamente as credenciais. Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.
    
3. Skype para negócios começa emparelhamento com o Lync VDI plug-in. Enquanto isso acontece, o cliente exibe dois ícones do Skype para a barra de status de negócios. O ícone na parte inferior esquerda indica que nenhuma dispositivos de áudio estão disponíveis e o ícone intermitente no canto inferior direito indica que o emparelhamento de VDI está em andamento: um. Depois que o emparelhamento de VDI for bem-sucedida, os ícones mudarão para indicar o dispositivo de áudio que será usado para chamadas e o êxito do emparelhamento de VDI: b. O usuário agora pode ver sua presença no Skype para dispositivos compatíveis de negócios que estão conectados ao computador local e fazer e atender chamadas como de costume.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Solução de problemas do plug-in VDI do Lync
<a name="tshoot_VDI"> </a>

Consulte as seções a seguir se houver problemas após a instalação do plug-in Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemas na instalação do plug-in VDI do Lync 

Se houver problemas com a instalação do plug-in Lync VDI, verifique o seguinte:
  
- Verifique se há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.
    
- Verifique se a proteção contra gravação está desativada. Consulte a documentação do fabricante do dispositivo para obter instruções.
    
### <a name="troubleshooting-issues-with-pairing"></a>Solução de problemas de emparelhamento

Quando o pareamento plug-in Lync VDI falhar, o ícone de pareamento no inferior direito é exibido como um "X" vermelho como mostrado: 
  
Veja a seguir os possíveis motivos das falhas e as ações que você pode tomar para corrigir o problema.  
  
- **O usuário inseriu credenciais incorretas durante a entrada.**
    
    O usuário deve sair do Skype para negócios e entrar novamente com as credenciais corretas. A caixa de diálogo de emparelhamento será exibida novamente e mostrará se o emparelhamento foi bem-sucedido.
    
- **Outra instância do cliente de área de trabalho remota está sendo executada.**
    
    Caso estejam usando Conexão de área de trabalho remota no Windows, os usuários devem fazer o seguinte:
    
1. Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete** e depois clicar em **Iniciar Gerenciador de Tarefas**.
    
2. Clicar na guia **Processos** e procurar todos os processos chamados **mstsc.exe** na lista.
    
3. Realçar cada processo **mstsc.exe** e clicar em **Finalizar Processo**.  
    
4. Iniciar uma nova sessão de área de trabalho remota e tentar conectar-se novamente.  
    
- **Os arquivos necessários não foram instalados corretamente.**
    
    Depois que o plug-in for instalado no computador local, verifique se estes arquivos estão presentes em C:\Arquivos de Programas\Microsoft Office\Office15 (ou na letra da unidade apropriada):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **O Skype para o cliente de negócios está sendo executado no computador local.**
    
    Para usar o Lync VDI plug-in, que um Skype para o cliente de negócios não deve estar executando no computador local, caso contrário, emparelhamento irá falhar. Como prática recomendada, o usuário não deve instalar um Skype para o cliente de negócios no computador local.
    
## <a name="see-also"></a>Ver também
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)