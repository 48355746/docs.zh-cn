---
title: TextFieldParser 不支持包含空格的注释标记
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: a8931d67cd728cf98bc4d83044c65fad6642b021
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252800"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser 不支持包含空格的注释标记
提供了包含空格的注释标记。 `TextFieldParser` 不支持包含空格的注释标记，除非空格出现在标记的开头。 出现在标记开头的空格将被忽略。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   提供正确的注释标记。  
  
## <a name="see-also"></a>请参阅

- [TextFieldParser.CommentTokens 属性](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)  
- [使用 TextFieldParser 对象分析文本文件](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
- [TextFieldParser 对象](../../visual-basic/language-reference/objects/textfieldparser-object.md)
