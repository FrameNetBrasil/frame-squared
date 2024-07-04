# Frame²

This repo contains the scripts and data related to the Frame² dataset.

The dataset comprises of three [JSON Lines](https://jsonlines.org/) files. One for visual objects [data/VO.jsonl](data/VO.jsonl) and two for textual annotation: [data/PT.jsonl](data/PT.jsonl) and [data/EN.jsonl](data/EN.jsonl).

## Visual annotations

The visual annotations file consists of a list of objects similar to this:

```
{
  "episode": 1,
  "objectId": 313136,
  "objectTimespan": [850.36, 852.76],
  "frame": "People_by_origin",
  "frameElement": "Person",
  "boundingBoxes": [
    [850.36, 120.0, 22.0, 617.0, 444.0],
    ...
  ]
}
```

## Transcription Annotations

The textual annotation follow the following format:

```
{
  "episode": 2,
  "sentenceId": 214710,
  "sentenceTimespan": [899.3, 902.2],
  "sentence": "Two hot dogs .",
  "tokens": ["Two", "hot", "dogs", "."],
  "frames": [
    {
      "id": "Cardinal_numbers",
      "span": [0, 0],
      "frameElements": [{ "id": "Entity", "span": [1, 2] }]
    }
  ]
}
```

The ```episode``` field identifies the Pedro Pelo Mundo episode where that object appears.
The ```objectTimespan``` and ```sentenceTimeSpan``` fields are a tuple that representing the start and end miliseconds of the video where that object or trasncription appears/is spoken.
```frame``` and ```frameElement``` are the actual FrameNet entities that the visual object represents. The ```frames``` field in text annotation represents a list of all frames evoked by that sentence and their frame elements. Their labels are identified by the ```id``` field and the ```span``` field informs the tokens that evoked the frame or are the frame elements.
Finally, ```boundingBoxes``` is an array of variable size (with at least one element). Each element is a 5-tuple representing a fixed time point where that bounding box appears and the four other numbers to represent the box itself. It's a tuple of ```(milisecond, x, y, width, heigh)```. Where the video resolution is 854 x 480 (or 480p).

## How to cite

Frederico Belcavello, Tiago Timponi Torrent, Ely E. Matos, Adriana S. Pagano, Maucha Gamonal, Natalia Sigiliano, Lívia Vicente Dutra, Helen de Andrade Abreu, Mairon Samagaio, Mariane Carvalho, Franciany Campos, Gabrielly Azalim, Bruna Mazzei, Mateus Fonseca de Oliveira, Ana Carolina Loçasso Luz, Lívia Pádua Ruiz, Júlia Bellei, Amanda Pestana, Josiane Costa, et al.. 2024. [Frame2: A FrameNet-based Multimodal Dataset for Tackling Text-image Interactions in Video](https://aclanthology.org/2024.lrec-main.655). In Proceedings of the 2024 Joint International Conference on Computational Linguistics, Language Resources and Evaluation (LREC-COLING 2024), pages 7429–7437, Torino, Italia. ELRA and ICCL.

## License

This dataset is shared under a [CC BY-NC 4.0 DEED license](https://creativecommons.org/licenses/by-nc/4.0/deed.en).
