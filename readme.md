Roadmap – Accelerarea inferenței YOLOv8n cu TensorRT pe Jetson Orin Nano
Obiectiv: Implementarea unei aplicații de detecție a obiectelor cu YOLOv8n pe NVIDIA Jetson Orin Nano și evaluarea optimizărilor aduse de TensorRT FP16 și CUDA.
Etapa 1 — 28 octombrie–3 noiembrie: Configurarea mediului
•	Verific mediul software și configurația plăcii Jetson.
•	Configurez repository-ul GitHub și structura proiectului.
•	Verific disponibilitatea PyTorch, TensorRT și CUDA.
•	Rulez YOLOv8n pe o imagine și salvez rezultatul.
Livrabil: mediu verificat și prima detecție funcțională.
Etapa 2 — 4–10 noiembrie: Modelul de referință
•	Rulez YOLOv8n în PyTorch FP32.
•	Export modelul în ONNX și verific rezultatele.
•	Pregătesc un set fix de imagini pentru testare.
•	Creez scripturile pentru compararea predicțiilor și măsurarea performanței.
Livrabil: model de referință funcțional și set de testare pregătit.
Etapa 3 — 11–24 noiembrie: Integrarea TensorRT
•	Construiesc motorul TensorRT FP32 pe Jetson.
•	Integrez și testez varianta TensorRT FP16.
•	Compar detecțiile cu rezultatele PyTorch.
•	Măsor latența și verific diferențele de acuratețe.
Livrabil: versiuni TensorRT funcționale și primele rezultate comparative.
Etapa 4 — 25 noiembrie–8 decembrie: Optimizarea CUDA
•	Implementez preprocesarea CUDA.
•	Implementez decodarea ieșirilor YOLO cu CUDA.
•	Validez rezultatele față de implementarea de referință.
•	Integrez componentele în aplicație și măsor impactul asupra timpului total de execuție.
•	Dacă timpul permite, încerc optimizarea NMS pe GPU și a transferurilor de date.
Livrabil: pipeline integrat cu TensorRT și CUDA, testat pe Jetson.
Etapa 5 — 9–16 decembrie: Testare și documentare
•	Rulez benchmark-ul final pentru toate variantele funcționale.
•	Compar latența, FPS-ul, consumul de memorie și acuratețea.
•	Calculez speedup-ul față de implementarea de referință.
•	Salvez rezultatele în CSV și generez grafice comparative.
•	Finalizez README-ul, raportul și demonstrația proiectului.








Săptămâna 1 • 28 octombrie–3 noiembrie
Setup
•	README.md — descrierea proiectului și obiectivul.
•	docs/environment.md — configurația Jetson și versiunile software disponibile.
•	scripts/test_environment.py — verificarea mediului, dacă este posibil.
•	results/first_detection.jpg — prima imagine cu detecțiile YOLOv8n.
La final: repository-ul este organizat și aM prima detecție funcțională.
Săptămâna 2 • 4–10 noiembrie
Referință
•	scripts/pytorch_inference.py — inferență în PyTorch FP32.
•	scripts/export_onnx.py — exportul modelului în ONNX.
•	scripts/compare_outputs.py — compararea predicțiilor.
•	models/README.md — instrucțiuni pentru obținerea modelului.
La final: pot rula modelul de referință și pot verifica exportul ONNX.
Săptămâna 3 • 11–17 noiembrie
TensorRT FP32
•	scripts/build_engine.py — construirea motorului TensorRT, dacă procesul poate fi automatizat.
•	scripts/tensorrt_inference.py — inferența TensorRT FP32.
•	results/initial_benchmark.csv — primele măsurători.
•	Actualizare docs/environment.md cu pașii de instalare și rulare.
La final: am o primă versiune TensorRT FP32 funcțională sau documentezi clar blocajele întâmpinate.
Săptămâna 4 • 18–24 noiembrie
TensorRT FP16
•	Suport pentru varianta TensorRT FP16.
•	scripts/benchmark.py — măsurarea comparativă a variantelor disponibile.
•	results/tensorrt_comparison.csv — comparație PyTorch, TensorRT FP32 și FP16.
•	Actualizare README cu rezultatele inițiale.
La final: am primele rezultate comparative între variantele funcționale.
Săptămâna 5 • 25 noiembrie–1 decembrie
CUDA
•	cuda/preprocess.cu — kerneluri pentru preprocesare.
•	cuda/preprocess_test.cpp — testarea kernelurilor, dacă este fezabilă.
•	results/cuda_validation.csv — comparația cu referința CPU.
La final: am prima operație CUDA implementată și validată.
Săptămâna 6 • 2–8 decembrie
Integrare
•	cuda/postprocess.cu — decodarea ieșirilor YOLO, dacă este implementată.
•	Integrarea preprocesării și postprocesării în pipeline.
•	results/pipeline_benchmark.csv — timpii măsurați pentru etapele aplicației.
La final: am pipeline-ul integrat sau o variantă funcțională cu componentele CUDA realizate până atunci.
Săptămâna 7 • 9–15 decembrie
Benchmark final
•	results/final_benchmark.csv — măsurătorile finale.
•	results/plots/ — graficele comparative.
•	docs/results.md — interpretarea rezultatelor.
•	demo/ — capturi sau un videoclip scurt al aplicației.
La final: am rezultate reproductibile și o comparație clară între variante.
16 decembrie • Predare
•	README complet, cu instrucțiuni de instalare și rulare.
•	docs/report.pdf — raportul final.
•	Repository verificat și organizat. 
 
