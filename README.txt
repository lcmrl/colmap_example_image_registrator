Example usage of image registrator with COLMAP (https://github.com/colmap/colmap):
1. Initial reconstruction in folder "reconstruction_5_images"
2. Copied the ./reconstruction_5_images/initial_db.db into ./reconstruction_6_images/final_db.db
3. ./reconstruction_6_images/imgs contain all images (also the new one)
4. ./reconstruction_6_images/new_images.txt contains the new image to be added to the reconstruction
5. colmap feature_extractor --database_path ./reconstruction_6_images/final_db.db --image_path ./reconstruction_6_images/imgs --image_list_path ./reconstruction_6_images/new_images.txt
6. colmap vocab_tree_matcher --database_path ./reconstruction_6_images/final_db.db --VocabTreeMatching.vocab_tree_path path_to_vocab_tree
7. colmap image_registrator --database_path ./reconstruction_6_images/final_db.db --input_path ./reconstruction_5_images/initial_sparse --output_path ./reconstruction_6_images/output_path

For the example images from the ENRICH dataset have been used. For many other datasets with accurate ground truth see https://github.com/davidemarelli/ENRICH