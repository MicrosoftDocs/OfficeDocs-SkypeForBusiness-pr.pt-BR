---
title: Notas de versão
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artigo discute as melhorias cumulativas em sistemas de sala Skype v2.
ms.openlocfilehash: ddcc4da301d491d763baf736053fd8eaeaee1b87
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375503"
---
# <a name="release-notes"></a>Notas de versão 

Este artigo discute as melhorias cumulativas em sistemas de sala Skype v2.


##  <a name="version-history"></a>Histórico de versão

| Versão | Publicado em <br>Repositório da Microsoft | 
| ---     | ---  |
| 4.0.27.0 |  10/1/2018    | 
| 4.0.19.0 |  08/31/2018    |   
| 4.0.18.0 |  27/08/2018    |   
| 4.0.8.0 |  07/06/2018    |   
| 3.1.115.0|  18/06/2018    |
| 3.1.113.0|  13/06/2018    |   
| 3.1.112.0|  05/06/2018    |   
| 3.1.104.0|  16/04/2018    |            
| 3.1.100.0|  03/16/2018    |            
| 3.1.99.0 | 14/3/2018      |  
| 3.1.98.0    | 3/8/2018    |   
|  3.0.16.0    |  27/11/2017   |
| 3.0.15.0 | 10/3/2017  |            
| 3.0.12.0 |  9/1/2017  |            
| 3.0.8.0 | 11/16/2017 | 
| 3.0.6.0 | 11/16/2017 | 
| 2.0.2.0  | 15/03/2017 | 
| RTM (1.0.8) | 12/7/2016  | 


## <a name="skype-room-systems-v2-feature-introduction-and-issue-resolution"></a>Sistemas de sala Skype v2 recurso Introdução e resoluções de problemas

### <a name="40270-1012018"></a>4.0.27.0 (1/10/2018)
Introduzido nessa atualização: 
- Alterações de código necessárias para preparar o aplicativo SRSv2 atualização do Windows 10 versão 1803 posterior
- Corrigir o problema de formatação com os EULA localizados - especificamente norueguês - que impede avançando além da janela de instalação de EULA OOBE
- Alterações de código necessárias para fazer com que o aplicativo do Skype sala sistemas v2 executados nos sistemas herdados de sala Lync. Ver mais [aqui](https://aka.ms/lrsupgrade).
 

### <a name="40190-8312018"></a>4.0.19.0 (31/8/2018)
Introduzido nessa atualização: 
- Hotfix para o aplicativo Crestron não launching que normalmente pode ser acessado pressionando o botão do aplicativo em dispositivos Crestron SR. Após a instalação do 4.0.19.0 é necessário reiniciar o aplicativo SRSv2 

### <a name="40180-08272018"></a>4.0.18.0 (27/08/2018)
Introduzido nessa atualização: 
- Aprimoramentos de recurso "Informar sobre um problema" no modo de equipes (equivalente "Forneça Feedback" no Skype para o modo de negócios)
- Habilitar capacidade para fallback de equipes Skype para o modo de negócios para chamadas SIP
- Aprimoramentos de acessibilidade (o Narrator, Lente de aumento)
- Reiniciar automaticamente app quando necessário depois que tiverem sido aplicadas alterações de provisionamento de XML
- Correções Miscellaneous

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)
Introduzido nessa atualização: 
- Essa atualização permite que ambos os Skype para negócios *e* equipes reuniões suporte nos dispositivos de sistemas de sala.  As equipes está desativado por padrão, depois que a atualização for aplicada.  Os administradores podem habilitar equipes localmente nas configurações do dispositivo ou através de um envio xml remoto.

### <a name="311150-06182018"></a>3.1.115.0 (18/06/2018)
Introduzido nessa atualização: 
- Corrigi a erros de endereço observado em alguns sistemas durante a inicialização do aplicativo.

### <a name="311130-06132018"></a>3.1.113.0 (13/06/2018)
Introduzido nessa atualização: 
- Habilitando Microsoft mais flexibilidade de alterações gerenciar atualizações do Windows.
- Nenhuma alteração a experiência do usuário final.

### <a name="311120-06052018"></a>3.1.112.0 (05/06/2018)
Introduzido nessa atualização: 
- Corrigir a capacidade de resposta de console do endereço da inclusão problemas observados em dispositivos baseados em Surface Pro de 2017 conectados a dois frente de sala exibe e vídeo
- Seleção automatizada para garantir que o sistema está executando o script de provisionamento mais recente.

### <a name="311040-04162018"></a>3.1.104.0 (16/04/2018)
Introduzido nessa atualização: 
- Corrigir para melhorar OSK (teclado virtual) comportamento em sistemas baseados em janela 10 versão 1709
- Aprimoramentos para se preparar para atualizações futuras do sistema operacional

### <a name="311000-03162018"></a>3.1.100.0 (16/03/2018)
Introduzido nessa atualização:  
- Atualizado para melhorar a telemetria de aplicativo.

### <a name="31990-03142018"></a>3.1.99.0 (14/03/2018)
Introduzido nessa atualização: 
- Correções um problema onde de participação da reunião intermitente problemas podem ocorrer.
- Corrige um problema conhecido por resultar em uma experiência de "congelamento do dispositivo".

### <a name="31980--382018"></a>3.1.98.0 (8/3/2018)
Introduzido nessa atualização: 
- Correções para melhorar a estabilidade de bug/travamento
- Suporte para o console de tamanho variável
- Processamento de áudio periférico descarregamento (lista de exceções de mídia adicionais)
- Otimizações que habilitará a profissionais de TI a criação de imagens de tipo faça você mesmo com a atualização de janeiro de Windows 10 versão 1709 e posterior.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (27/11/2017)
Introduzido nessa atualização:  
- Resolve um problema com o recurso de "Fornecer comentários".

### <a name="30150-1032017"></a>3.0.15.0 (3/10/2017)
Introduzido nessa atualização: 
- Suporte para a [Série de MSR Polycom](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) encaixa o hardware
- Suporte para o [Logitech Brio](https://www.logitech.com/en-us/product/brio)
- Resolve um problema onde exibe (console e frente da sala) falha para entrar no modo de suspensão quando não há nenhuma atividade na sala.


### <a name="30120-912017"></a>3.0.12.0 (1/9/2017)
Introduzido nessa atualização:   
- É executado em um tablet (2017) Surface Pro  
- Oferece suporte a atualização do criador do Windows 10 Enterprise (idioma inglês, compilação 1703)    
- Suporte para [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) encaixa o hardware    
- Suporte de OEM para controles do ambiente (Crestron)
    
A versão de 64 bits do edition de aniversário no Windows 10 Enterprise (idioma inglês, versão 1607) não é mais suportada a partir de sistemas de sala Skype v2 versão 3.0.12.0 (atualização de 3). 

### <a name="3080-842017"></a>3.0.8.0 (4/8/2017) 
Introduzido nessa atualização: 
- Resolve problemas observados quando procurando por usuários através do campo de pesquisa participantes federados. Anterior para essa correção, os resultados da pesquisa para usuários federados externos não podem ter resolvido corretamente e em vez disso retornado resultados incorretos. 

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017) 
Introduzido nessa atualização: 
- Suporte de tela dual (para correspondência de sistema herdado)   
- Themability (temas internos e a capacidade de definir o tema personalizado) 
- Capacidade de fazer comentários para compilações públicas     
- Telemetria aprimorada em torno de confiabilidade de participação da reunião     
- Relatórios de OMS adicionais     
- Capacidade do administrador de TI configurar dispositivos remotamente<!--  - Front-of-Room UX shows room details pre-meeting U2  --> 


### <a name="2020-03152017"></a>2.0.2.0 (15/03/2017)
Introduzido nessa atualização: 
- Seleção de usuário no aplicativo de dispositivos USB de áudio e vídeos de sala de reunião
- Integrado status da sala console relatórios para clientes usando o pacote de gerenciamento do Microsoft Operations (consulte [management v2 de sistemas de sala Skype planejar com OMS](oms-management.md)) 

### <a name="release-to-market--1272016"></a>Versão ao mercado (7/12/2016)
**Recursos:** 

 **Projetado para o Skype for Business**
  
- Reuniões do Skype com apenas um toque    
- Experiência de Reunião do Skype otimizada para salas com vídeo HD de preenchimento de tela e áudio de banda larga HD
- Todos os participantes podem se conectar à Reunião do Skype usando o dispositivo que quiserem, onde quer que estejam
- Convide pessoas a partir de seu diretório, onde você pode ver imediatamente a disponibilidade de cada contato, ou por chamada telefônica
- Compatível com os recursos de Conferência e Chamada PSTN do Skype for Business para substituir o telefone de conferência em sua sala
    
  **Transforme qualquer sala de reunião**
  
- Aplicativo dedicado à Reunião do Skype, otimizado para o controlador de tela touch de centro da mesa e para a grande tela frontal da sala
- Aproveite os investimentos existentes em seus projetores ou na tela frontal da sala
- Funciona para todos os tipos de espaços de reunião, de espaços pequenos a grandes salas de conferência
- Os dispositivos de áudio e vídeo certificados do Skype for Business estão disponíveis para vários tamanhos de sala
- Ingestão interna com fio para projetar o compartilhamento de área de trabalho para a sala e para a Reunião do Skype
    
  **Fácil de implantar, simples de gerenciar**
  
- Dispositivo sempre ativo que aciona as telas automaticamente quando detecta pessoas na sala
- Implantação e atualização simples do aplicativo de Reunião do Skype da UWP (Plataforma Universal do Windows)
- O Windows AppLocker bloqueia o dispositivo para o aplicativo de Reunião do Skype
- Monitorado e gerenciado como um dispositivo do Windows 10 Enterprise via Intune e SCCM (MDM)
- Confiabilidade de nível empresarial
- Esforço mínimo para usuários finais devido à semelhança com a interface do usuário do Skype
- É executado no tablet Surface Pro 4
 

<a name="See"> </a>  
## <a name="see-also"></a>Ver também

[Ajuda da versão 2 de sistemas de sala do Skype](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparar seu Skype para ambiente de negócios](srs-v2-prep.md)

[Suporte para sistemas de sala Skype v2 atuais filial versões](srs2-lifecycle-support.md)

[Problemas conhecidos para sistemas de sala Skype v2](../../manage/skype-room-systems-v2/known-issues.md)

[Planejar o Skype Room Systems versão 2](skype-room-systems-v2-0.md)

[Gerenciar o Skype Room Systems versão 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
